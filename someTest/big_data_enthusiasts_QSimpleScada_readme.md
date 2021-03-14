# QSimpleScada
Qt/C++ based simple SCADA framework, with dashboard, static and dynamic components. By using QSimpleScada framework you can build complex SCADA uis for your needs.

# Minimum requirements
Qt 5.8

# Installing with qpm
Just use qpm (http://u.720life.cn/g/2b4a1992d7fbbbffac01eb3aa131d1f5fbd9500a6df61f2e0d66632458e0b379) to install QSimpleScada in your project. Run qpm install com.indeema.QSimpleScada . in *.pro file include(vendor/Vendor.pri)

Or Compile QSimpleScada with QSimpleScada pro file, you will receive QSimpleScadaLib folder with compiled windows or macos libs.

# Sample

You can check example that uses QSimpleScada https://github.com/IndeemaSoftware/QSimpleScadaSample

# Sample in action
 

# How to start

Create editable QScadaBoard
```cpp
QScadaBoard *mBoard = new QScadaBoard(this);
mBoard->setEditable(true);
```

You can connect to signals, to handle events
```cpp
signals:
    void objectDoubleClicked(QScadaObject*);
    void objectSelected(QScadaObject *);
```

So now you can create some default QScadaObject on the board
```cpp
mBoard->createNewObject();
```
Or create object with specific parameters
```cpp
QScadaObjectInfo *lInfo = new QScadaObjectInfo();
lInfo->setId(2);
lInfo->setBackGroundImage(":/resources/some_structure.png");
lInfo->setShowBackgroundImage(true);
lInfo->setShowMarkers(false);
```

Creating object with specific parameters could be useful when restoring dashboard from project file.

Also you have possibility to send object to front or to back
```cpp
void MainWindow::bringToFront()
{
    if (!mBoard->getSeletedObjects().isEmpty()) {
        QScadaObject *lObject = mBoard->getSeletedObjects().first();
        mBoard->bringToFront(lObject);
    }
}

void MainWindow::sendToBack()
{
    if (!mBoard->getSeletedObjects().isEmpty()) {
        QScadaObject *lObject = mBoard->getSeletedObjects().first();
        mBoard->sendToBack(lObject);
    }
}
```

Also save and open project file
```cpp
void MainWindow::save()
{
    QFileDialog lDialog(this);
    lDialog.setFileMode(QFileDialog::AnyFile);
    lDialog.setAcceptMode(QFileDialog::AcceptSave);
    lDialog.setDirectory(QDir::currentPath());
    lDialog.setWindowTitle(tr("Save Project"));
    lDialog.setNameFilter(tr("iReDS Project (*.irp)"));

    QScadaBoardInfo *lBoardInfo = new QScadaBoardInfo();
    QScadaBoardController *lController = new QScadaBoardController();
    QScadaDeviceInfo lDeviceInfo;

    if (lDialog.exec() == QDialog::Accepted) {
        QStringList lFiles = lDialog.selectedFiles();
        if (lFiles.count() > 0) {
            QString lFileName = lFiles.at(0);
            if (!lFileName.contains(".irp")) {
                lFileName.append(".irp");
            }
            QStringList lIps;
            for (QScadaObject *object :*mBoard->objects()) {
                lBoardInfo->appendObjectInfo(object->info());
            }
            QList  lBoardInfoList;
            lBoardInfoList.append(lBoardInfo);

            lController->initConnectedDevices(lBoardInfoList);

            lDeviceInfo.setName("Test Device");
            lDeviceInfo.setIp(QHostAddress("127.0.0.0"));
            QList  lList;
            lList.append(lDeviceInfo);
            QString lDevices = VConnectedDeviceInfo::XMLFromDeviceInfo(lList, lController);   // setEditable(true);
}

void MainWindow::open()
{
    QString lFileName = QFileDialog::getOpenFileName(this,
        tr("Open Project"), QDir::currentPath(), tr("iReDS Project (*.irp)"));

    if (!lFileName.isEmpty()) {
        mObjectInfoDialog->updateWithObjectInfo(nullptr);

        for (QScadaObject *object : *mBoard->objects()) {
                mBoard->deleteObject(object);
        }

        VConnectedDeviceInfo* lConnectedDevceInfo = new VConnectedDeviceInfo();
        QByteArray lRawData;
        QFile lFile(lFileName);
        if (lFile.open(QIODevice::ReadOnly | QIODevice::Text)) {
            QTextStream lStreamFileOut(&lFile);
            lStreamFileOut.setCodec("UTF-8");
            lRawData = lStreamFileOut.readAll().toUtf8();
            lFile.close();

            lConnectedDevceInfo->initFromXml(lRawData);

            for (int i = 0; i  connecteDeviceList.count(); ++i) {
                for (QScadaBoardInfo *boardInfo : lConnectedDevceInfo->connecteDeviceList.at(i)->boardList) {
                    if (boardInfo != nullptr) {
                        mBoard->setEditable(false);
                        for (QScadaObjectInfo *info : boardInfo->objectList()) {
                            mBoard->createNewObject(info);
                        }
                    }
                }
            }

            mBoard->update();
            mBoard->setEditable(true);
        } else {
            qDebug()   " << lFile.fileName();
        }

        delete lConnectedDevceInfo;
    }
}
```

## Communication and Support
If you encounter an issue or you have any comments or propositions with using the QSimpleScada library then you can reach us in several different ways:
- Having difficulties with using QSimpleScada you can write at [Stackoverflow](http://u.720life.cn/g/87bbd50441ad714fa4b3a92b06a390573fc86eb7d24a082f77a1e4ba31fd4b29) or at [Qt forum](http://u.720life.cn/g/0806a537e56f3425b85acec2abe88b65eb88d6ab4e112d29a027ecc2593cc6cc). Don't forget about specifing the **QSimpleScada** tag. You will be helped by the community of this resource or our specialists will help you with an answer.

- If you find a bug and want to tell us about it - specify it in the section [Issues](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046079b54ada1a19a235c7c855aed2c98aa7badb5bcec3cd1d9abdb654897fabed1e20dbb0b9e5820e7469d5d369df97198).
In this section, we only consider bugs and ignore any questions relating to the support.

- For additional assistance with your project - please contact us at **support@indeema.com** and specify **QSimpleScada** in the subject line.

- You can also follow our news at [@IndeemaSoftware](http://u.720life.cn/g/5ea88169c4a0fbd169233d52478d54fe9c131a3c261369a245147044c72b683b37aacf488abae1d5bb5496c8de43137a) or on our [blog](http://u.720life.cn/g/39e5f48c0e2903046094063d07df1f72fc3750d8b67f74948abcfc6f66f58983).

- For further questions on cooperation, simply email us at **support@indeema.com**.

## License
**QSimpleScada** works under the MIT license. For more information see [here](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046079b54ada1a19a235c7c855aed2c98aa7badb5bcec3cd1d9abdb654897fabed1e85baf2700595984577c8bdb6abbd15e574e2309381b6c69c731219eac578eaf).

## Terms
**QSimpleScada** is released for testing purposes only. We make no guarantees with respect to its function. By using this software you agree that Indeema is not liable for any damage to your system and data.

To know more about us and our [IoT expertise](http://u.720life.cn/g/39e5f48c0e2903046094063d07df1f7228bdccfa2a04f8110143046409be9a52), visit our website http://indeema.com




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6efb8aa05c80ee17c06f084775adf7826a3b9bb79f30c75406112bf9405af19dce81797025f735907d201bdc466ae5a49bb7bb2c57e5e02dcf7e37900567a4c6f1)