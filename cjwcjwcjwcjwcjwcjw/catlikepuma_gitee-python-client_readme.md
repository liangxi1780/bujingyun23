## Requirements.

Python 2.7 and 3.4+

## Installation & Usage
### pip install

Then import the package:
```python
import gitee_client 
```

### Setuptools

Install via [Setuptools](http://u.720life.cn/g/d2f0970cf3b517fef9748f67f9f0955912dcf1e89703ef5d196796846c62e4d2b637d97cedc0d5e58eeb85a1d19c9106).

```sh
python setup.py install --user
```
(or `sudo python setup.py install` to install the package for all users)

Then import the package:
```python
import gitee_client
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```python
# coding: utf-8

"""
    码云 Open API



    OpenAPI spec version: 5.0.1
    

"""

from __future__ import absolute_import

import unittest

import gitee_client
from gitee_client.apis.auth_api import AuthApi


class TestAuthApi(unittest.TestCase):
    """ AuthApi unit test stubs """

    def setUp(self):
        self.api = gitee_client.apis.auth_api.AuthApi()

    def tearGetToken(self):
        response = self.api.get_token("邮箱",
                                      "密码",
                                      "回调地址",
                                      "clientID",
                                      "client_secert",
                                      "user_info projects pull_requests issues notes keys hook groups gists")
        print(response["access_token"])
        pass


if __name__ == '__main__':
    unittest.main()


```

## Documentation for API Endpoints

All URIs are relative to *https://gitee.com/api*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*ActivityApi* | [**delete_v5_user_starred_owner_repo**](docs/ActivityApi.md#delete_v5_user_starred_owner_repo) | **DELETE** /v5/user/starred/{owner}/{repo} | 取消 star 一个项目
*ActivityApi* | [**delete_v5_user_subscriptions_owner_repo**](docs/ActivityApi.md#delete_v5_user_subscriptions_owner_repo) | **DELETE** /v5/user/subscriptions/{owner}/{repo} | 取消 watch 一个项目
*ActivityApi* | [**get_v5_events**](docs/ActivityApi.md#get_v5_events) | **GET** /v5/events | 获取站内所有公开动态
*ActivityApi* | [**get_v5_networks_owner_repo_events**](docs/ActivityApi.md#get_v5_networks_owner_repo_events) | **GET** /v5/networks/{owner}/{repo}/events | 列出项目的所有公开动态
*ActivityApi* | [**get_v5_notifications_messages**](docs/ActivityApi.md#get_v5_notifications_messages) | **GET** /v5/notifications/messages | 列出授权用户的所有私信
*ActivityApi* | [**get_v5_notifications_messages_id**](docs/ActivityApi.md#get_v5_notifications_messages_id) | **GET** /v5/notifications/messages/{id} | 获取一个私信
*ActivityApi* | [**get_v5_notifications_threads**](docs/ActivityApi.md#get_v5_notifications_threads) | **GET** /v5/notifications/threads | 列出授权用户的所有通知
*ActivityApi* | [**get_v5_notifications_threads_id**](docs/ActivityApi.md#get_v5_notifications_threads_id) | **GET** /v5/notifications/threads/{id} | 获取一个通知
*ActivityApi* | [**get_v5_orgs_org_events**](docs/ActivityApi.md#get_v5_orgs_org_events) | **GET** /v5/orgs/{org}/events | 列出组织的公开动态
*ActivityApi* | [**get_v5_repos_owner_repo_events**](docs/ActivityApi.md#get_v5_repos_owner_repo_events) | **GET** /v5/repos/{owner}/{repo}/events | 列出项目的所有动态
*ActivityApi* | [**get_v5_repos_owner_repo_notifications**](docs/ActivityApi.md#get_v5_repos_owner_repo_notifications) | **GET** /v5/repos/{owner}/{repo}/notifications | 列出一个项目里的通知
*ActivityApi* | [**get_v5_repos_owner_repo_stargazers**](docs/ActivityApi.md#get_v5_repos_owner_repo_stargazers) | **GET** /v5/repos/{owner}/{repo}/stargazers | 列出 star 了项目的用户
*ActivityApi* | [**get_v5_repos_owner_repo_subscribers**](docs/ActivityApi.md#get_v5_repos_owner_repo_subscribers) | **GET** /v5/repos/{owner}/{repo}/subscribers | 列出 watch 了项目的用户
*ActivityApi* | [**get_v5_user_starred**](docs/ActivityApi.md#get_v5_user_starred) | **GET** /v5/user/starred | 列出授权用户 star 了的项目
*ActivityApi* | [**get_v5_user_starred_owner_repo**](docs/ActivityApi.md#get_v5_user_starred_owner_repo) | **GET** /v5/user/starred/{owner}/{repo} | 检查授权用户是否 star 了一个项目
*ActivityApi* | [**get_v5_user_subscriptions**](docs/ActivityApi.md#get_v5_user_subscriptions) | **GET** /v5/user/subscriptions | 列出授权用户 watch 了的项目
*ActivityApi* | [**get_v5_user_subscriptions_owner_repo**](docs/ActivityApi.md#get_v5_user_subscriptions_owner_repo) | **GET** /v5/user/subscriptions/{owner}/{repo} | 检查授权用户是否 watch 了一个项目
*ActivityApi* | [**get_v5_users_username_events**](docs/ActivityApi.md#get_v5_users_username_events) | **GET** /v5/users/{username}/events | 列出用户的动态
*ActivityApi* | [**get_v5_users_username_events_orgs_org**](docs/ActivityApi.md#get_v5_users_username_events_orgs_org) | **GET** /v5/users/{username}/events/orgs/{org} | 列出用户所属组织的动态
*ActivityApi* | [**get_v5_users_username_events_public**](docs/ActivityApi.md#get_v5_users_username_events_public) | **GET** /v5/users/{username}/events/public | 列出用户的公开动态
*ActivityApi* | [**get_v5_users_username_received_events**](docs/ActivityApi.md#get_v5_users_username_received_events) | **GET** /v5/users/{username}/received_events | 列出一个用户收到的动态
*ActivityApi* | [**get_v5_users_username_received_events_public**](docs/ActivityApi.md#get_v5_users_username_received_events_public) | **GET** /v5/users/{username}/received_events/public | 列出一个用户收到的公开动态
*ActivityApi* | [**get_v5_users_username_starred**](docs/ActivityApi.md#get_v5_users_username_starred) | **GET** /v5/users/{username}/starred | 列出用户 star 了的项目
*ActivityApi* | [**get_v5_users_username_subscriptions**](docs/ActivityApi.md#get_v5_users_username_subscriptions) | **GET** /v5/users/{username}/subscriptions | 列出用户 watch 了的项目
*ActivityApi* | [**patch_v5_notifications_messages_id**](docs/ActivityApi.md#patch_v5_notifications_messages_id) | **PATCH** /v5/notifications/messages/{id} | 标记一个私信为已读
*ActivityApi* | [**patch_v5_notifications_threads_id**](docs/ActivityApi.md#patch_v5_notifications_threads_id) | **PATCH** /v5/notifications/threads/{id} | 标记一个通知为已读
*ActivityApi* | [**post_v5_notifications_messages**](docs/ActivityApi.md#post_v5_notifications_messages) | **POST** /v5/notifications/messages | 发送私信给指定用户
*ActivityApi* | [**put_v5_notifications_messages**](docs/ActivityApi.md#put_v5_notifications_messages) | **PUT** /v5/notifications/messages | 标记所有私信为已读
*ActivityApi* | [**put_v5_notifications_threads**](docs/ActivityApi.md#put_v5_notifications_threads) | **PUT** /v5/notifications/threads | 标记所有通知为已读
*ActivityApi* | [**put_v5_repos_owner_repo_notifications**](docs/ActivityApi.md#put_v5_repos_owner_repo_notifications) | **PUT** /v5/repos/{owner}/{repo}/notifications | 标记一个项目里的通知为已读
*ActivityApi* | [**put_v5_user_starred_owner_repo**](docs/ActivityApi.md#put_v5_user_starred_owner_repo) | **PUT** /v5/user/starred/{owner}/{repo} | star 一个项目
*ActivityApi* | [**put_v5_user_subscriptions_owner_repo**](docs/ActivityApi.md#put_v5_user_subscriptions_owner_repo) | **PUT** /v5/user/subscriptions/{owner}/{repo} | watch 一个项目
*GistsApi* | [**delete_v5_gists_gist_id_comments_id**](docs/GistsApi.md#delete_v5_gists_gist_id_comments_id) | **DELETE** /v5/gists/{gist_id}/comments/{id} | 删除代码片段的评论
*GistsApi* | [**delete_v5_gists_id**](docs/GistsApi.md#delete_v5_gists_id) | **DELETE** /v5/gists/{id} | 删除该条代码片段
*GistsApi* | [**delete_v5_gists_id_star**](docs/GistsApi.md#delete_v5_gists_id_star) | **DELETE** /v5/gists/{id}/star | 取消Star代码片段
*GistsApi* | [**get_v5_gists**](docs/GistsApi.md#get_v5_gists) | **GET** /v5/gists | 获取代码片段
*GistsApi* | [**get_v5_gists_gist_id_comments**](docs/GistsApi.md#get_v5_gists_gist_id_comments) | **GET** /v5/gists/{gist_id}/comments | 获取代码片段的评论
*GistsApi* | [**get_v5_gists_gist_id_comments_id**](docs/GistsApi.md#get_v5_gists_gist_id_comments_id) | **GET** /v5/gists/{gist_id}/comments/{id} | 获取单条代码片段的评论
*GistsApi* | [**get_v5_gists_id**](docs/GistsApi.md#get_v5_gists_id) | **GET** /v5/gists/{id} | 获取单条代码片段
*GistsApi* | [**get_v5_gists_id_commits**](docs/GistsApi.md#get_v5_gists_id_commits) | **GET** /v5/gists/{id}/commits | 获取代码片段的commit
*GistsApi* | [**get_v5_gists_id_forks**](docs/GistsApi.md#get_v5_gists_id_forks) | **GET** /v5/gists/{id}/forks | 获取Fork该条代码片段的列表
*GistsApi* | [**get_v5_gists_id_star**](docs/GistsApi.md#get_v5_gists_id_star) | **GET** /v5/gists/{id}/star | 判断代码片段是否已Star
*GistsApi* | [**get_v5_gists_public**](docs/GistsApi.md#get_v5_gists_public) | **GET** /v5/gists/public | 获取公开的代码片段
*GistsApi* | [**get_v5_gists_starred**](docs/GistsApi.md#get_v5_gists_starred) | **GET** /v5/gists/starred | 获取用户Star的代码片段
*GistsApi* | [**get_v5_users_username_gists**](docs/GistsApi.md#get_v5_users_username_gists) | **GET** /v5/users/{username}/gists | 获取指定用户的公开代码片段
*GistsApi* | [**patch_v5_gists_gist_id_comments_id**](docs/GistsApi.md#patch_v5_gists_gist_id_comments_id) | **PATCH** /v5/gists/{gist_id}/comments/{id} | 修改代码片段的评论
*GistsApi* | [**patch_v5_gists_id**](docs/GistsApi.md#patch_v5_gists_id) | **PATCH** /v5/gists/{id} | 修改代码片段
*GistsApi* | [**post_v5_gists**](docs/GistsApi.md#post_v5_gists) | **POST** /v5/gists | 创建代码片段
*GistsApi* | [**post_v5_gists_gist_id_comments**](docs/GistsApi.md#post_v5_gists_gist_id_comments) | **POST** /v5/gists/{gist_id}/comments | 增加代码片段的评论
*GistsApi* | [**post_v5_gists_id_forks**](docs/GistsApi.md#post_v5_gists_id_forks) | **POST** /v5/gists/{id}/forks | Fork代码片段
*GistsApi* | [**put_v5_gists_id_star**](docs/GistsApi.md#put_v5_gists_id_star) | **PUT** /v5/gists/{id}/star | Star代码片段
*GitDataApi* | [**get_v5_repos_owner_repo_git_blobs_sha**](docs/GitDataApi.md#get_v5_repos_owner_repo_git_blobs_sha) | **GET** /v5/repos/{owner}/{repo}/git/blobs/{sha} | 获取文件Blob
*GitDataApi* | [**get_v5_repos_owner_repo_git_trees_sha**](docs/GitDataApi.md#get_v5_repos_owner_repo_git_trees_sha) | **GET** /v5/repos/{owner}/{repo}/git/trees/{sha} | 获取目录Tree
*IssuesApi* | [**delete_v5_repos_owner_repo_issues_comments_id**](docs/IssuesApi.md#delete_v5_repos_owner_repo_issues_comments_id) | **DELETE** /v5/repos/{owner}/{repo}/issues/comments/{id} | 删除Issue某条评论
*IssuesApi* | [**get_v5_issues**](docs/IssuesApi.md#get_v5_issues) | **GET** /v5/issues | 获取当前授权用户的所有Issue
*IssuesApi* | [**get_v5_orgs_org_issues**](docs/IssuesApi.md#get_v5_orgs_org_issues) | **GET** /v5/orgs/{org}/issues | 获取当前用户某个组织的Issues
*IssuesApi* | [**get_v5_repos_owner_repo_issues**](docs/IssuesApi.md#get_v5_repos_owner_repo_issues) | **GET** /v5/repos/{owner}/{repo}/issues | 项目的所有Issues
*IssuesApi* | [**get_v5_repos_owner_repo_issues_comments**](docs/IssuesApi.md#get_v5_repos_owner_repo_issues_comments) | **GET** /v5/repos/{owner}/{repo}/issues/comments | 获取项目所有Issue的评论
*IssuesApi* | [**get_v5_repos_owner_repo_issues_comments_id**](docs/IssuesApi.md#get_v5_repos_owner_repo_issues_comments_id) | **GET** /v5/repos/{owner}/{repo}/issues/comments/{id} | 获取项目Issue某条评论
*IssuesApi* | [**get_v5_repos_owner_repo_issues_number**](docs/IssuesApi.md#get_v5_repos_owner_repo_issues_number) | **GET** /v5/repos/{owner}/{repo}/issues/{number} | 项目的某个Issue
*IssuesApi* | [**get_v5_repos_owner_repo_issues_number_comments**](docs/IssuesApi.md#get_v5_repos_owner_repo_issues_number_comments) | **GET** /v5/repos/{owner}/{repo}/issues/{number}/comments | 获取项目某个Issue所有的评论
*IssuesApi* | [**get_v5_user_issues**](docs/IssuesApi.md#get_v5_user_issues) | **GET** /v5/user/issues | 获取当前授权用户的所有Issues
*IssuesApi* | [**patch_v5_repos_owner_repo_issues_comments_id**](docs/IssuesApi.md#patch_v5_repos_owner_repo_issues_comments_id) | **PATCH** /v5/repos/{owner}/{repo}/issues/comments/{id} | 更新Issue某条评论
*IssuesApi* | [**patch_v5_repos_owner_repo_issues_number**](docs/IssuesApi.md#patch_v5_repos_owner_repo_issues_number) | **PATCH** /v5/repos/{owner}/{repo}/issues/{number} | 更新Issue
*IssuesApi* | [**post_v5_repos_owner_repo_issues**](docs/IssuesApi.md#post_v5_repos_owner_repo_issues) | **POST** /v5/repos/{owner}/{repo}/issues | 创建Issue
*IssuesApi* | [**post_v5_repos_owner_repo_issues_number_comments**](docs/IssuesApi.md#post_v5_repos_owner_repo_issues_number_comments) | **POST** /v5/repos/{owner}/{repo}/issues/{number}/comments | 创建某个Issue评论
*LabelsApi* | [**delete_v5_repos_owner_repo_issues_number_labels**](docs/LabelsApi.md#delete_v5_repos_owner_repo_issues_number_labels) | **DELETE** /v5/repos/{owner}/{repo}/issues/{number}/labels | 删除Issue所有标签
*LabelsApi* | [**delete_v5_repos_owner_repo_issues_number_labels_name**](docs/LabelsApi.md#delete_v5_repos_owner_repo_issues_number_labels_name) | **DELETE** /v5/repos/{owner}/{repo}/issues/{number}/labels/{name} | 删除Issue标签
*LabelsApi* | [**delete_v5_repos_owner_repo_labels_name**](docs/LabelsApi.md#delete_v5_repos_owner_repo_labels_name) | **DELETE** /v5/repos/{owner}/{repo}/labels/{name} | 删除一个项目标签
*LabelsApi* | [**get_v5_repos_owner_repo_issues_number_labels**](docs/LabelsApi.md#get_v5_repos_owner_repo_issues_number_labels) | **GET** /v5/repos/{owner}/{repo}/issues/{number}/labels | 获取项目Issue的所有标签
*LabelsApi* | [**get_v5_repos_owner_repo_labels**](docs/LabelsApi.md#get_v5_repos_owner_repo_labels) | **GET** /v5/repos/{owner}/{repo}/labels | 获取项目所有标签
*LabelsApi* | [**get_v5_repos_owner_repo_labels_name**](docs/LabelsApi.md#get_v5_repos_owner_repo_labels_name) | **GET** /v5/repos/{owner}/{repo}/labels/{name} | 根据标签名称获取单个标签
*LabelsApi* | [**patch_v5_repos_owner_repo_labels_original_name**](docs/LabelsApi.md#patch_v5_repos_owner_repo_labels_original_name) | **PATCH** /v5/repos/{owner}/{repo}/labels/{original_name} | 更新一个项目标签
*LabelsApi* | [**post_v5_repos_owner_repo_issues_number_labels**](docs/LabelsApi.md#post_v5_repos_owner_repo_issues_number_labels) | **POST** /v5/repos/{owner}/{repo}/issues/{number}/labels | 创建Issue标签
*LabelsApi* | [**post_v5_repos_owner_repo_labels**](docs/LabelsApi.md#post_v5_repos_owner_repo_labels) | **POST** /v5/repos/{owner}/{repo}/labels | 创建项目标签
*LabelsApi* | [**put_v5_repos_owner_repo_issues_number_labels**](docs/LabelsApi.md#put_v5_repos_owner_repo_issues_number_labels) | **PUT** /v5/repos/{owner}/{repo}/issues/{number}/labels | 替换Issue所有标签
*MilestonesApi* | [**delete_v5_repos_owner_repo_milestones_number**](docs/MilestonesApi.md#delete_v5_repos_owner_repo_milestones_number) | **DELETE** /v5/repos/{owner}/{repo}/milestones/{number} | 删除项目单个里程碑
*MilestonesApi* | [**get_v5_repos_owner_repo_milestones**](docs/MilestonesApi.md#get_v5_repos_owner_repo_milestones) | **GET** /v5/repos/{owner}/{repo}/milestones | 获取项目所有里程碑
*MilestonesApi* | [**get_v5_repos_owner_repo_milestones_number**](docs/MilestonesApi.md#get_v5_repos_owner_repo_milestones_number) | **GET** /v5/repos/{owner}/{repo}/milestones/{number} | 获取项目单个里程碑
*MilestonesApi* | [**patch_v5_repos_owner_repo_milestones_number**](docs/MilestonesApi.md#patch_v5_repos_owner_repo_milestones_number) | **PATCH** /v5/repos/{owner}/{repo}/milestones/{number} | 更新项目里程碑
*MilestonesApi* | [**post_v5_repos_owner_repo_milestones**](docs/MilestonesApi.md#post_v5_repos_owner_repo_milestones) | **POST** /v5/repos/{owner}/{repo}/milestones | 创建项目里程碑
*MiscellaneousApi* | [**get_v5_emojis**](docs/MiscellaneousApi.md#get_v5_emojis) | **GET** /v5/emojis | 列出可使用的 Emoji
*MiscellaneousApi* | [**get_v5_gitignore_templates**](docs/MiscellaneousApi.md#get_v5_gitignore_templates) | **GET** /v5/gitignore/templates | 列出可使用的 .gitignore 模板
*MiscellaneousApi* | [**get_v5_gitignore_templates_name**](docs/MiscellaneousApi.md#get_v5_gitignore_templates_name) | **GET** /v5/gitignore/templates/{name} | 获取一个 .gitignore 模板
*MiscellaneousApi* | [**get_v5_gitignore_templates_name_raw**](docs/MiscellaneousApi.md#get_v5_gitignore_templates_name_raw) | **GET** /v5/gitignore/templates/{name}/raw | 获取一个 .gitignore 模板原始文件
*MiscellaneousApi* | [**get_v5_licenses**](docs/MiscellaneousApi.md#get_v5_licenses) | **GET** /v5/licenses | 列出可使用的开源许可协议
*MiscellaneousApi* | [**get_v5_licenses_license**](docs/MiscellaneousApi.md#get_v5_licenses_license) | **GET** /v5/licenses/{license} | 获取一个开源许可协议
*MiscellaneousApi* | [**get_v5_licenses_license_raw**](docs/MiscellaneousApi.md#get_v5_licenses_license_raw) | **GET** /v5/licenses/{license}/raw | 获取一个开源许可协议原始文件
*MiscellaneousApi* | [**get_v5_repos_owner_repo_license**](docs/MiscellaneousApi.md#get_v5_repos_owner_repo_license) | **GET** /v5/repos/{owner}/{repo}/license | 获取一个项目使用的开源许可协议
*MiscellaneousApi* | [**post_v5_markdown**](docs/MiscellaneousApi.md#post_v5_markdown) | **POST** /v5/markdown | 渲染 Markdown 文本
*OrganizationsApi* | [**delete_v5_orgs_org_memberships_username**](docs/OrganizationsApi.md#delete_v5_orgs_org_memberships_username) | **DELETE** /v5/orgs/{org}/memberships/{username} | 移除授权用户所管理组织中的成员
*OrganizationsApi* | [**delete_v5_user_memberships_orgs_org**](docs/OrganizationsApi.md#delete_v5_user_memberships_orgs_org) | **DELETE** /v5/user/memberships/orgs/{org} | 退出一个组织
*OrganizationsApi* | [**get_v5_orgs_org**](docs/OrganizationsApi.md#get_v5_orgs_org) | **GET** /v5/orgs/{org} | 获取一个组织
*OrganizationsApi* | [**get_v5_orgs_org_members**](docs/OrganizationsApi.md#get_v5_orgs_org_members) | **GET** /v5/orgs/{org}/members | 列出一个组织的所有成员
*OrganizationsApi* | [**get_v5_orgs_org_memberships_username**](docs/OrganizationsApi.md#get_v5_orgs_org_memberships_username) | **GET** /v5/orgs/{org}/memberships/{username} | 获取授权用户所属组织的一个成员
*OrganizationsApi* | [**get_v5_user_memberships_orgs**](docs/OrganizationsApi.md#get_v5_user_memberships_orgs) | **GET** /v5/user/memberships/orgs | 列出授权用户在所属组织的成员资料
*OrganizationsApi* | [**get_v5_user_memberships_orgs_org**](docs/OrganizationsApi.md#get_v5_user_memberships_orgs_org) | **GET** /v5/user/memberships/orgs/{org} | 获取授权用户在一个组织的成员资料
*OrganizationsApi* | [**get_v5_user_orgs**](docs/OrganizationsApi.md#get_v5_user_orgs) | **GET** /v5/user/orgs | 列出授权用户所属的组织
*OrganizationsApi* | [**get_v5_users_username_orgs**](docs/OrganizationsApi.md#get_v5_users_username_orgs) | **GET** /v5/users/{username}/orgs | 列出用户所属的组织
*OrganizationsApi* | [**patch_v5_orgs_org**](docs/OrganizationsApi.md#patch_v5_orgs_org) | **PATCH** /v5/orgs/{org} | 更新授权用户所管理的组织资料
*OrganizationsApi* | [**patch_v5_user_memberships_orgs_org**](docs/OrganizationsApi.md#patch_v5_user_memberships_orgs_org) | **PATCH** /v5/user/memberships/orgs/{org} | 更新授权用户在一个组织的成员资料
*OrganizationsApi* | [**put_v5_orgs_org_memberships_username**](docs/OrganizationsApi.md#put_v5_orgs_org_memberships_username) | **PUT** /v5/orgs/{org}/memberships/{username} | 增加或更新授权用户所管理组织的成员
*PullRequestsApi* | [**delete_v5_repos_owner_repo_pulls_comments_id**](docs/PullRequestsApi.md#delete_v5_repos_owner_repo_pulls_comments_id) | **DELETE** /v5/repos/{owner}/{repo}/pulls/comments/{id} | 删除评论
*PullRequestsApi* | [**delete_v5_repos_owner_repo_pulls_number_requested_reviewers**](docs/PullRequestsApi.md#delete_v5_repos_owner_repo_pulls_number_requested_reviewers) | **DELETE** /v5/repos/{owner}/{repo}/pulls/{number}/requested_reviewers | 移除审查人员
*PullRequestsApi* | [**get_v5_repos_owner_repo_pulls**](docs/PullRequestsApi.md#get_v5_repos_owner_repo_pulls) | **GET** /v5/repos/{owner}/{repo}/pulls | 获取Pull Request列表
*PullRequestsApi* | [**get_v5_repos_owner_repo_pulls_comments**](docs/PullRequestsApi.md#get_v5_repos_owner_repo_pulls_comments) | **GET** /v5/repos/{owner}/{repo}/pulls/comments | 获取该项目下的所有Pull Request评论
*PullRequestsApi* | [**get_v5_repos_owner_repo_pulls_comments_id**](docs/PullRequestsApi.md#get_v5_repos_owner_repo_pulls_comments_id) | **GET** /v5/repos/{owner}/{repo}/pulls/comments/{id} | 获取Pull Request的某个评论
*PullRequestsApi* | [**get_v5_repos_owner_repo_pulls_number**](docs/PullRequestsApi.md#get_v5_repos_owner_repo_pulls_number) | **GET** /v5/repos/{owner}/{repo}/pulls/{number} | 获取单个Pull Request
*PullRequestsApi* | [**get_v5_repos_owner_repo_pulls_number_comments**](docs/PullRequestsApi.md#get_v5_repos_owner_repo_pulls_number_comments) | **GET** /v5/repos/{owner}/{repo}/pulls/{number}/comments | 获取某个Pull Request的所有评论
*PullRequestsApi* | [**get_v5_repos_owner_repo_pulls_number_commits**](docs/PullRequestsApi.md#get_v5_repos_owner_repo_pulls_number_commits) | **GET** /v5/repos/{owner}/{repo}/pulls/{number}/commits | 获取某Pull Request的所有Commit信息。最多显示250条Commit
*PullRequestsApi* | [**get_v5_repos_owner_repo_pulls_number_files**](docs/PullRequestsApi.md#get_v5_repos_owner_repo_pulls_number_files) | **GET** /v5/repos/{owner}/{repo}/pulls/{number}/files | Pull Request Commit文件列表。最多显示300条diff
*PullRequestsApi* | [**get_v5_repos_owner_repo_pulls_number_merge**](docs/PullRequestsApi.md#get_v5_repos_owner_repo_pulls_number_merge) | **GET** /v5/repos/{owner}/{repo}/pulls/{number}/merge | 判断Pull Request是否已经合并
*PullRequestsApi* | [**get_v5_repos_owner_repo_pulls_number_requested_reviewers**](docs/PullRequestsApi.md#get_v5_repos_owner_repo_pulls_number_requested_reviewers) | **GET** /v5/repos/{owner}/{repo}/pulls/{number}/requested_reviewers | 获取审查人员的列表
*PullRequestsApi* | [**patch_v5_repos_owner_repo_pulls_comments_id**](docs/PullRequestsApi.md#patch_v5_repos_owner_repo_pulls_comments_id) | **PATCH** /v5/repos/{owner}/{repo}/pulls/comments/{id} | 编辑评论
*PullRequestsApi* | [**patch_v5_repos_owner_repo_pulls_number**](docs/PullRequestsApi.md#patch_v5_repos_owner_repo_pulls_number) | **PATCH** /v5/repos/{owner}/{repo}/pulls/{number} | 更新Pull Request信息
*PullRequestsApi* | [**post_v5_repos_owner_repo_pulls**](docs/PullRequestsApi.md#post_v5_repos_owner_repo_pulls) | **POST** /v5/repos/{owner}/{repo}/pulls | 创建Pull Request
*PullRequestsApi* | [**post_v5_repos_owner_repo_pulls_number_comments**](docs/PullRequestsApi.md#post_v5_repos_owner_repo_pulls_number_comments) | **POST** /v5/repos/{owner}/{repo}/pulls/{number}/comments | 提交Pull Request评论
*PullRequestsApi* | [**post_v5_repos_owner_repo_pulls_number_requested_reviewers**](docs/PullRequestsApi.md#post_v5_repos_owner_repo_pulls_number_requested_reviewers) | **POST** /v5/repos/{owner}/{repo}/pulls/{number}/requested_reviewers | 增加审查人员
*PullRequestsApi* | [**put_v5_repos_owner_repo_pulls_number_merge**](docs/PullRequestsApi.md#put_v5_repos_owner_repo_pulls_number_merge) | **PUT** /v5/repos/{owner}/{repo}/pulls/{number}/merge | 合并Pull Request
*RepositoriesApi* | [**delete_v5_repos_owner_repo**](docs/RepositoriesApi.md#delete_v5_repos_owner_repo) | **DELETE** /v5/repos/{owner}/{repo} | 删除一个项目
*RepositoriesApi* | [**delete_v5_repos_owner_repo_branches_branch_protection**](docs/RepositoriesApi.md#delete_v5_repos_owner_repo_branches_branch_protection) | **DELETE** /v5/repos/{owner}/{repo}/branches/{branch}/protection | 取消保护分支的设置
*RepositoriesApi* | [**delete_v5_repos_owner_repo_collaborators_username**](docs/RepositoriesApi.md#delete_v5_repos_owner_repo_collaborators_username) | **DELETE** /v5/repos/{owner}/{repo}/collaborators/{username} | 移除项目成员
*RepositoriesApi* | [**delete_v5_repos_owner_repo_comments_id**](docs/RepositoriesApi.md#delete_v5_repos_owner_repo_comments_id) | **DELETE** /v5/repos/{owner}/{repo}/comments/{id} | 删除Commit评论
*RepositoriesApi* | [**delete_v5_repos_owner_repo_contents_path**](docs/RepositoriesApi.md#delete_v5_repos_owner_repo_contents_path) | **DELETE** /v5/repos/{owner}/{repo}/contents/{path} | 删除文件
*RepositoriesApi* | [**delete_v5_repos_owner_repo_keys_id**](docs/RepositoriesApi.md#delete_v5_repos_owner_repo_keys_id) | **DELETE** /v5/repos/{owner}/{repo}/keys/{id} | 删除一个项目公钥
*RepositoriesApi* | [**delete_v5_repos_owner_repo_releases_id**](docs/RepositoriesApi.md#delete_v5_repos_owner_repo_releases_id) | **DELETE** /v5/repos/{owner}/{repo}/releases/{id} | 删除项目Release
*RepositoriesApi* | [**get_v5_orgs_org_repos**](docs/RepositoriesApi.md#get_v5_orgs_org_repos) | **GET** /v5/orgs/{org}/repos | 获取一个组织的项目
*RepositoriesApi* | [**get_v5_repos_owner_repo**](docs/RepositoriesApi.md#get_v5_repos_owner_repo) | **GET** /v5/repos/{owner}/{repo} | 列出授权用户的某个项目
*RepositoriesApi* | [**get_v5_repos_owner_repo_branches**](docs/RepositoriesApi.md#get_v5_repos_owner_repo_branches) | **GET** /v5/repos/{owner}/{repo}/branches | 获取所有分支
*RepositoriesApi* | [**get_v5_repos_owner_repo_branches_branch**](docs/RepositoriesApi.md#get_v5_repos_owner_repo_branches_branch) | **GET** /v5/repos/{owner}/{repo}/branches/{branch} | 获取单个分支
*RepositoriesApi* | [**get_v5_repos_owner_repo_collaborators**](docs/RepositoriesApi.md#get_v5_repos_owner_repo_collaborators) | **GET** /v5/repos/{owner}/{repo}/collaborators | 获取项目的所有成员
*RepositoriesApi* | [**get_v5_repos_owner_repo_collaborators_username**](docs/RepositoriesApi.md#get_v5_repos_owner_repo_collaborators_username) | **GET** /v5/repos/{owner}/{repo}/collaborators/{username} | 判断用户是否为项目成员
*RepositoriesApi* | [**get_v5_repos_owner_repo_collaborators_username_permission**](docs/RepositoriesApi.md#get_v5_repos_owner_repo_collaborators_username_permission) | **GET** /v5/repos/{owner}/{repo}/collaborators/{username}/permission | 查看项目成员的权限
*RepositoriesApi* | [**get_v5_repos_owner_repo_comments**](docs/RepositoriesApi.md#get_v5_repos_owner_repo_comments) | **GET** /v5/repos/{owner}/{repo}/comments | 获取项目的Commit评论
*RepositoriesApi* | [**get_v5_repos_owner_repo_comments_id**](docs/RepositoriesApi.md#get_v5_repos_owner_repo_comments_id) | **GET** /v5/repos/{owner}/{repo}/comments/{id} | 获取项目的某条Commit评论
*RepositoriesApi* | [**get_v5_repos_owner_repo_commits**](docs/RepositoriesApi.md#get_v5_repos_owner_repo_commits) | **GET** /v5/repos/{owner}/{repo}/commits | 项目的所有提交
*RepositoriesApi* | [**get_v5_repos_owner_repo_commits_ref_comments**](docs/RepositoriesApi.md#get_v5_repos_owner_repo_commits_ref_comments) | **GET** /v5/repos/{owner}/{repo}/commits/{ref}/comments | 获取单个Commit的评论
*RepositoriesApi* | [**get_v5_repos_owner_repo_commits_sha**](docs/RepositoriesApi.md#get_v5_repos_owner_repo_commits_sha) | **GET** /v5/repos/{owner}/{repo}/commits/{sha} | 项目的某个提交
*RepositoriesApi* | [**get_v5_repos_owner_repo_compare_base___head**](docs/RepositoriesApi.md#get_v5_repos_owner_repo_compare_base___head) | **GET** /v5/repos/{owner}/{repo}/compare/{base}...{head} | 两个Commits之间对比的版本差异
*RepositoriesApi* | [**get_v5_repos_owner_repo_contents_path**](docs/RepositoriesApi.md#get_v5_repos_owner_repo_contents_path) | **GET** /v5/repos/{owner}/{repo}/contents(/{path}) | 获取仓库具体路径下的内容
*RepositoriesApi* | [**get_v5_repos_owner_repo_contributors**](docs/RepositoriesApi.md#get_v5_repos_owner_repo_contributors) | **GET** /v5/repos/{owner}/{repo}/contributors | 获取项目贡献者
*RepositoriesApi* | [**get_v5_repos_owner_repo_forks**](docs/RepositoriesApi.md#get_v5_repos_owner_repo_forks) | **GET** /v5/repos/{owner}/{repo}/forks | 查看项目的Forks
*RepositoriesApi* | [**get_v5_repos_owner_repo_keys**](docs/RepositoriesApi.md#get_v5_repos_owner_repo_keys) | **GET** /v5/repos/{owner}/{repo}/keys | 展示项目的公钥
*RepositoriesApi* | [**get_v5_repos_owner_repo_keys_id**](docs/RepositoriesApi.md#get_v5_repos_owner_repo_keys_id) | **GET** /v5/repos/{owner}/{repo}/keys/{id} | 获取项目的单个公钥
*RepositoriesApi* | [**get_v5_repos_owner_repo_pages**](docs/RepositoriesApi.md#get_v5_repos_owner_repo_pages) | **GET** /v5/repos/{owner}/{repo}/pages | 获取Pages信息
*RepositoriesApi* | [**get_v5_repos_owner_repo_readme**](docs/RepositoriesApi.md#get_v5_repos_owner_repo_readme) | **GET** /v5/repos/{owner}/{repo}/readme | 获取仓库README
*RepositoriesApi* | [**get_v5_repos_owner_repo_releases**](docs/RepositoriesApi.md#get_v5_repos_owner_repo_releases) | **GET** /v5/repos/{owner}/{repo}/releases | 获取项目的所有Releases
*RepositoriesApi* | [**get_v5_repos_owner_repo_releases_id**](docs/RepositoriesApi.md#get_v5_repos_owner_repo_releases_id) | **GET** /v5/repos/{owner}/{repo}/releases/{id} | 获取项目的单个Releases
*RepositoriesApi* | [**get_v5_repos_owner_repo_releases_latest**](docs/RepositoriesApi.md#get_v5_repos_owner_repo_releases_latest) | **GET** /v5/repos/{owner}/{repo}/releases/latest | 获取项目的最后更新的Release
*RepositoriesApi* | [**get_v5_repos_owner_repo_releases_tags_tag**](docs/RepositoriesApi.md#get_v5_repos_owner_repo_releases_tags_tag) | **GET** /v5/repos/{owner}/{repo}/releases/tags/{tag} | 根据Tag名称获取项目的Release
*RepositoriesApi* | [**get_v5_repos_owner_repo_tags**](docs/RepositoriesApi.md#get_v5_repos_owner_repo_tags) | **GET** /v5/repos/{owner}/{repo}/tags | 列出项目所有的tags
*RepositoriesApi* | [**get_v5_user_repos**](docs/RepositoriesApi.md#get_v5_user_repos) | **GET** /v5/user/repos | 列出授权用户的所有项目
*RepositoriesApi* | [**get_v5_users_username_repos**](docs/RepositoriesApi.md#get_v5_users_username_repos) | **GET** /v5/users/{username}/repos | 获取某个用户的公开项目
*RepositoriesApi* | [**patch_v5_repos_owner_repo**](docs/RepositoriesApi.md#patch_v5_repos_owner_repo) | **PATCH** /v5/repos/{owner}/{repo} | 更新项目设置
*RepositoriesApi* | [**patch_v5_repos_owner_repo_comments_id**](docs/RepositoriesApi.md#patch_v5_repos_owner_repo_comments_id) | **PATCH** /v5/repos/{owner}/{repo}/comments/{id} | 更新Commit评论
*RepositoriesApi* | [**patch_v5_repos_owner_repo_releases_id**](docs/RepositoriesApi.md#patch_v5_repos_owner_repo_releases_id) | **PATCH** /v5/repos/{owner}/{repo}/releases/{id} | 更新项目Release
*RepositoriesApi* | [**post_v5_orgs_org_repos**](docs/RepositoriesApi.md#post_v5_orgs_org_repos) | **POST** /v5/orgs/{org}/repos | 创建组织项目
*RepositoriesApi* | [**post_v5_repos_owner_repo_commits_sha_comments**](docs/RepositoriesApi.md#post_v5_repos_owner_repo_commits_sha_comments) | **POST** /v5/repos/{owner}/{repo}/commits/{sha}/comments | 创建Commit评论
*RepositoriesApi* | [**post_v5_repos_owner_repo_contents_path**](docs/RepositoriesApi.md#post_v5_repos_owner_repo_contents_path) | **POST** /v5/repos/{owner}/{repo}/contents/{path} | 新建文件
*RepositoriesApi* | [**post_v5_repos_owner_repo_forks**](docs/RepositoriesApi.md#post_v5_repos_owner_repo_forks) | **POST** /v5/repos/{owner}/{repo}/forks | Fork一个项目
*RepositoriesApi* | [**post_v5_repos_owner_repo_keys**](docs/RepositoriesApi.md#post_v5_repos_owner_repo_keys) | **POST** /v5/repos/{owner}/{repo}/keys | 为项目添加公钥
*RepositoriesApi* | [**post_v5_repos_owner_repo_pages_builds**](docs/RepositoriesApi.md#post_v5_repos_owner_repo_pages_builds) | **POST** /v5/repos/{owner}/{repo}/pages/builds | 请求建立Pages
*RepositoriesApi* | [**post_v5_repos_owner_repo_releases**](docs/RepositoriesApi.md#post_v5_repos_owner_repo_releases) | **POST** /v5/repos/{owner}/{repo}/releases | 创建项目Release
*RepositoriesApi* | [**post_v5_user_repos**](docs/RepositoriesApi.md#post_v5_user_repos) | **POST** /v5/user/repos | 创建一个项目
*RepositoriesApi* | [**put_v5_repos_owner_repo_branches_branch_protection**](docs/RepositoriesApi.md#put_v5_repos_owner_repo_branches_branch_protection) | **PUT** /v5/repos/{owner}/{repo}/branches/{branch}/protection | 设置分支保护
*RepositoriesApi* | [**put_v5_repos_owner_repo_collaborators_username**](docs/RepositoriesApi.md#put_v5_repos_owner_repo_collaborators_username) | **PUT** /v5/repos/{owner}/{repo}/collaborators/{username} | 添加项目成员
*RepositoriesApi* | [**put_v5_repos_owner_repo_contents_path**](docs/RepositoriesApi.md#put_v5_repos_owner_repo_contents_path) | **PUT** /v5/repos/{owner}/{repo}/contents/{path} | 更新文件
*UsersApi* | [**delete_v5_user_following_username**](docs/UsersApi.md#delete_v5_user_following_username) | **DELETE** /v5/user/following/{username} | 取消关注一个用户
*UsersApi* | [**delete_v5_user_keys_id**](docs/UsersApi.md#delete_v5_user_keys_id) | **DELETE** /v5/user/keys/{id} | 删除一个公钥
*UsersApi* | [**delete_v5_user_unconfirmed_email**](docs/UsersApi.md#delete_v5_user_unconfirmed_email) | **DELETE** /v5/user/unconfirmed_email | 删除授权用户未激活的邮箱地址
*UsersApi* | [**get_v5_user**](docs/UsersApi.md#get_v5_user) | **GET** /v5/user | 获取授权用户的资料
*UsersApi* | [**get_v5_user_address**](docs/UsersApi.md#get_v5_user_address) | **GET** /v5/user/address | 获取授权用户的地理信息
*UsersApi* | [**get_v5_user_emails**](docs/UsersApi.md#get_v5_user_emails) | **GET** /v5/user/emails | 获取授权用户的邮箱地址
*UsersApi* | [**get_v5_user_followers**](docs/UsersApi.md#get_v5_user_followers) | **GET** /v5/user/followers | 列出授权用户的关注者
*UsersApi* | [**get_v5_user_following**](docs/UsersApi.md#get_v5_user_following) | **GET** /v5/user/following | 列出授权用户正关注的用户
*UsersApi* | [**get_v5_user_following_username**](docs/UsersApi.md#get_v5_user_following_username) | **GET** /v5/user/following/{username} | 检查授权用户是否关注了一个用户
*UsersApi* | [**get_v5_user_keys**](docs/UsersApi.md#get_v5_user_keys) | **GET** /v5/user/keys | 列出授权用户的所有公钥
*UsersApi* | [**get_v5_user_keys_id**](docs/UsersApi.md#get_v5_user_keys_id) | **GET** /v5/user/keys/{id} | 获取一个公钥
*UsersApi* | [**get_v5_users_username**](docs/UsersApi.md#get_v5_users_username) | **GET** /v5/users/{username} | 获取一个用户
*UsersApi* | [**get_v5_users_username_followers**](docs/UsersApi.md#get_v5_users_username_followers) | **GET** /v5/users/{username}/followers | 列出指定用户的关注者
*UsersApi* | [**get_v5_users_username_following**](docs/UsersApi.md#get_v5_users_username_following) | **GET** /v5/users/{username}/following | 列出指定用户正在关注的用户
*UsersApi* | [**get_v5_users_username_following_target_user**](docs/UsersApi.md#get_v5_users_username_following_target_user) | **GET** /v5/users/{username}/following/{target_user} | 检查指定用户是否关注目标用户
*UsersApi* | [**get_v5_users_username_keys**](docs/UsersApi.md#get_v5_users_username_keys) | **GET** /v5/users/{username}/keys | 列出指定用户的所有公钥
*UsersApi* | [**patch_v5_user**](docs/UsersApi.md#patch_v5_user) | **PATCH** /v5/user | 更新授权用户的资料
*UsersApi* | [**patch_v5_user_address**](docs/UsersApi.md#patch_v5_user_address) | **PATCH** /v5/user/address | 更新授权用户的地理信息
*UsersApi* | [**post_v5_user_emails**](docs/UsersApi.md#post_v5_user_emails) | **POST** /v5/user/emails | 添加授权用户的新邮箱地址
*UsersApi* | [**post_v5_user_keys**](docs/UsersApi.md#post_v5_user_keys) | **POST** /v5/user/keys | 添加一个公钥
*UsersApi* | [**put_v5_user_following_username**](docs/UsersApi.md#put_v5_user_following_username) | **PUT** /v5/user/following/{username} | 关注一个用户
*WebhooksApi* | [**delete_v5_repos_owner_repo_hooks_id**](docs/WebhooksApi.md#delete_v5_repos_owner_repo_hooks_id) | **DELETE** /v5/repos/{owner}/{repo}/hooks/{id} | 删除一个项目WebHook
*WebhooksApi* | [**get_v5_repos_owner_repo_hooks**](docs/WebhooksApi.md#get_v5_repos_owner_repo_hooks) | **GET** /v5/repos/{owner}/{repo}/hooks | 列出项目的WebHooks
*WebhooksApi* | [**get_v5_repos_owner_repo_hooks_id**](docs/WebhooksApi.md#get_v5_repos_owner_repo_hooks_id) | **GET** /v5/repos/{owner}/{repo}/hooks/{id} | 获取项目单个WebHook
*WebhooksApi* | [**patch_v5_repos_owner_repo_hooks_id**](docs/WebhooksApi.md#patch_v5_repos_owner_repo_hooks_id) | **PATCH** /v5/repos/{owner}/{repo}/hooks/{id} | 更新一个项目WebHook
*WebhooksApi* | [**post_v5_repos_owner_repo_hooks**](docs/WebhooksApi.md#post_v5_repos_owner_repo_hooks) | **POST** /v5/repos/{owner}/{repo}/hooks | 创建一个项目WebHook
*WebhooksApi* | [**post_v5_repos_owner_repo_hooks_id_tests**](docs/WebhooksApi.md#post_v5_repos_owner_repo_hooks_id_tests) | **POST** /v5/repos/{owner}/{repo}/hooks/{id}/tests | 测试WebHook是否发送成功


## Documentation For Models

 - [Blob](docs/Blob.md)
 - [Branch](docs/Branch.md)
 - [Code](docs/Code.md)
 - [CodeComment](docs/CodeComment.md)
 - [CodeForks](docs/CodeForks.md)
 - [CodeForksHistory](docs/CodeForksHistory.md)
 - [Commit](docs/Commit.md)
 - [CommitContent](docs/CommitContent.md)
 - [Compare](docs/Compare.md)
 - [CompleteBranch](docs/CompleteBranch.md)
 - [Content](docs/Content.md)
 - [ContentBasic](docs/ContentBasic.md)
 - [Event](docs/Event.md)
 - [Group](docs/Group.md)
 - [GroupDetail](docs/GroupDetail.md)
 - [GroupMember](docs/GroupMember.md)
 - [Hook](docs/Hook.md)
 - [Issue](docs/Issue.md)
 - [Label](docs/Label.md)
 - [Milestone](docs/Milestone.md)
 - [Project](docs/Project.md)
 - [ProjectBasic](docs/ProjectBasic.md)
 - [PullRequest](docs/PullRequest.md)
 - [PullRequestComments](docs/PullRequestComments.md)
 - [PullRequestCommits](docs/PullRequestCommits.md)
 - [PullRequestFiles](docs/PullRequestFiles.md)
 - [Release](docs/Release.md)
 - [RepoCommit](docs/RepoCommit.md)
 - [SSHKey](docs/SSHKey.md)
 - [SSHKeyBasic](docs/SSHKeyBasic.md)
 - [Tree](docs/Tree.md)
 - [User](docs/User.md)
 - [UserAddress](docs/UserAddress.md)
 - [UserBasic](docs/UserBasic.md)
 - [UserDetail](docs/UserDetail.md)
 - [UserEmail](docs/UserEmail.md)
 - [UserMessage](docs/UserMessage.md)
 - [UserNotification](docs/UserNotification.md)


## Documentation For Authorization

 All endpoints do not require authorization.


## Author






 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e827f1de301d7fb56861b0e0535189ed6ac1f07818d68191b8f4ff296bf6024431390a0feb46481f621b9f9f28e39000a0d0b1cb23595af317f7a6fbaa86c5f8b)