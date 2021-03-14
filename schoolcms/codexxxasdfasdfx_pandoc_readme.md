 

# Pandoc

[![github
release](http://u.720life.cn/g/547fb4d6e23e13c922d5174f883a884b231dc797ab489417c3cdd966b58d1945155ce0c3fd90df543d6bd3678eca317a03ffa49e32028626f3eaefa8f76763e4c4d561cb7894877badac14cae00d8b60)]https://github.com/jgm/pandoc/releases
[![hackage
release](http://u.720life.cn/g/547fb4d6e23e13c922d5174f883a884bf84e46a39759d4020c7320e2c07461f1eb2347933f572bd840ac3b3161eaa6b42e344d6163fc89016c7f0e38e38133fc)]http://hackage.haskell.org/package/pandoc
[![homebrew](https://img.shields.io/homebrew/v/pandoc.svg)](http://brewformulas.org/Pandoc)
[![stackage LTS
package](http://u.720life.cn/g/c02ac323e895f1deb639403579337632dc509e00688b96c6706fd0df9303c5987682290f0de8d6c0e581291d01220755)]http://stackage.org/lts/package/pandoc
[![CircleCI](https://circleci.com/gh/jgm/pandoc.svg?style=svg)](https://circleci.com/gh/jgm/pandoc)
[![CI
tests](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465effe182bf9e1dce2e94da96f0d2bbe4a6d293ca7eccddb7774ff767bf50364a10c47d701f3f59190c2d469de1ad1329)]https://github.com/jgm/pandoc/actions
[![license](https://img.shields.io/badge/license-GPLv2+-lightgray.svg)](https://www.gnu.org/licenses/gpl.html)
[![pandoc-discuss on google
groups](http://u.720life.cn/g/547fb4d6e23e13c922d5174f883a884b69a0bb66f426f420bb8c064c5281b13807006e011b29b03e3f3bd1aca3def2bd2db3d505ee173dc0ee41e2467b1e8d32)]https://groups.google.com/forum/#!forum/pandoc-discuss

## The universal markup converter

Pandoc is a [Haskell](http://u.720life.cn/g/a8b789e16095301748f62a3cd954e3dce555f21aca279ecc97e453d071fbf676) library for converting from
one markup format to another, and a command-line tool that uses this
library. It can convert *from*

 

  - `commonmark` ([CommonMark](http://u.720life.cn/g/6a3398b216073104d9b8e03a9a8bd6d74cffe559dde5d93acdcbc2eb636fa98f) Markdown)
  - `creole` ([Creole 1.0](http://u.720life.cn/g/c449668bcc5e4ab37a0d2ddff3d024378a6d3150dd1f73c46b26eb770f9dd86c21dcfb8b23828c95fd0bcc29b44f96ec)
  - `csv` ([CSV](http://u.720life.cn/g/a6fc20f29c5b3b6059eab4d4320b2e4d5ea9eeef2572e4e8d60bb6a26cdeb2fee67063247ade3f64c122dda023d12359) table)
  - `docbook` ([DocBook](http://u.720life.cn/g/890ce3872016873bfc76c1e59963112abf0f3738fd32903977ddab66112446f2)
  - `docx` ([Word docx](http://u.720life.cn/g/dbf1195f8a53209e138d24666db06636e0c08fc9e8f56801f010d7db1f767118401a9d6660a8d5eeacc95ed29bc02797)
  - `dokuwiki` ([DokuWiki markup](http://u.720life.cn/g/bdefa628914765a0ba7e2e060ca080323d135b5c3b66a9f6a7796cbbfe4124efeca51501303051316b22010173dc892d)
  - `epub` ([EPUB](http://u.720life.cn/g/4e8e216fb28b4e0e354e4a3412be0e00c63cf2311edc33e01b0128c866cf80d2)
  - `fb2`
    ([FictionBook2](http://u.720life.cn/g/b07ed9589153fc6334836a5769a49bd4d7ef39cad333ac14279a2a0074b5666828d6b154e78213b5bf444ad0034e84e97b9d8889c4772c4db0259a85bc26444484c3068f2eb725a923437b6f396201ed)
    e-book)
  - `gfm` ([GitHub-Flavored
    Markdown](http://u.720life.cn/g/1f425b0b33da40ebdfbaffd56fc94509ec09346c8015e0ae429751be8b3a78a5f9bd204a45e483731ccfaeb2b6a33217afd7e6c548399842104d2670e057aa31)
    or the deprecated and less accurate `markdown_github`; use
    [`markdown_github`](http://u.720life.cn/g/7a714ce062b52cc46cf9cbfa25cdbd19536c81a23f59226b9396bb48f1bcc9b1cf8c0ab74f00a4f87c291afec654824c)
    only if you need extensions not supported in
    [`gfm`](http://u.720life.cn/g/7a714ce062b52cc46cf9cbfa25cdbd19536c81a23f59226b9396bb48f1bcc9b1cf8c0ab74f00a4f87c291afec654824c).
  - `haddock` ([Haddock
    markup](http://u.720life.cn/g/aca3470af400f8736261e7011140fcbaa50dcb5b5965acf411421bc7c3a73b8f6e063893092db4cbef36bd1c5ecc70eefaa1f6c6293565912c1aad70d175a033)
  - `html` ([HTML](http://u.720life.cn/g/098598e75704e07d68eba0aa885b4c2b22683595de7cca95118d75fdd21f2875)
  - `ipynb` ([Jupyter
    notebook](http://u.720life.cn/g/f11471ff78faf3759e63ff190304a656513b0c9887495a0b96725c7f59667f0fea5231cf0a3dc5708334e07e45dea1c2)
  - `jats` ([JATS](http://u.720life.cn/g/99459ac3d318804737729e83f1d31d7235e546408008542bfb98218805e1c287) XML)
  - `jira`
    ([Jira](http://u.720life.cn/g/3b577f9c7a0abc5568a59f94744e84c7502b9c3aa8e45a3a1ef8343556cbf4e2552d5b4a119a977c2c270dd6988f249e1bc07a65d8f5e6f68570943cbbffbf746c725c2c68d935bb252e01c5d440823b)
    wiki markup)
  - `json` (JSON version of native AST)
  - `latex` ([LaTeX](http://u.720life.cn/g/75e2a56bd8dbabd4b75ca0fcf22ee7db782f8e859b4952d3a5bbe0a3b7a96526)
  - `markdown` ([Pandoc’s
    Markdown](http://u.720life.cn/g/7a714ce062b52cc46cf9cbfa25cdbd19f4c212ad5314ebc63337eee86e223654132ce077d9c5f722b13df17cd6751d76)
  - `markdown_mmd`
    ([MultiMarkdown](http://u.720life.cn/g/9f447cda710f5e9f711b7a3fe65d92db3d142bd2fa0975258ce52fb840990c00fa922238f01d16bb66ab8a570f79fe3e)
  - `markdown_phpextra` ([PHP Markdown
    Extra](http://u.720life.cn/g/a00c9ad3254a6af90eef4e252f73e5fb88a1b58654cd0d87908304d72f3999cce54fd259ff8a93e1cf823e5eb0f0db17)
  - `markdown_strict` (original unextended
    [Markdown](http://u.720life.cn/g/82291fd6e6f08f28feb38b9e617d6f3a9555915fb522fb5acf99d58f231f63ba078746518ed17b3a0bcfeb2e955daf11)
  - `mediawiki` ([MediaWiki
    markup](http://u.720life.cn/g/33ae8636533afbeb23c2ec718d33e8304c62c0359ef5da336bac2eefc75de78e4e0654701c60ea884ceba14fc901763c)
  - `man` ([roff man](http://u.720life.cn/g/f239eca7f6eff78ac365d5b3fd9a799b97444828250b15f2c3fb76b20af8765d)
  - `muse` ([Muse](http://u.720life.cn/g/c98f5b13222eb04fbe3598c1421bba53e1e12ea5e962a3795378e42a435c92c5368ac777e58d304ee4d5c3f5531a91bd)
  - `native` (native Haskell)
  - `odt` ([ODT](http://u.720life.cn/g/dbf1195f8a53209e138d24666db06636d6f052b9892c039d27bffc03ce117ae4d559bcaf521591ec57af90d9dd536ae5)
  - `opml` ([OPML](http://u.720life.cn/g/2683720fe0af69b75cfe3ead25f73dd2f4f8b01c37200a31c2fdb40b0b4812ed)
  - `org` ([Emacs Org mode](http://u.720life.cn/g/169b9a9f3410b0df5a61b092e133e6f711630f28ad8ed7544a5c1d13858c113f)
  - `rst`
    ([reStructuredText](http://u.720life.cn/g/dc1a85fb589ea64d06034278a19bb496f3a7ed283c801f6b11730ede23a17ffd4ce60d1830f2325e10acdd190be600f5699282955e71abbe7fed415486774d3f)
  - `t2t` ([txt2tags](http://u.720life.cn/g/2fa0037bb642d647011095f8ac870bd05a1de8c633fb7828f5e9a9a46309e224)
  - `textile` ([Textile](http://u.720life.cn/g/b987cef77882ec082b3e6d0fe87b7c3728cd4a457a76732fb5eb0d3ae9d8e14d930f1bb1fff11899792b29a0f6f1c0cd)
  - `tikiwiki` ([TikiWiki
    markup](http://u.720life.cn/g/25f5b881b675313603245968dee49b83308709040c85102c54cd73cf2f439d7a26952bd8a0643ca77024ef4f4a33242fa08e11f2e037b271ad84160b96b13715733c9b9785c6ddfc0aabec40487ac74e)
  - `twiki` ([TWiki
    markup](http://u.720life.cn/g/d4721cd7fa63a44c4599ac3073e1dc24195c3f99ccc4f32daddf8c06cc4ed546cd0bb1b8ee742220949e99e46e5386b90d14045c6af44e292425ef5ee9fbbeb9)
  - `vimwiki` ([Vimwiki](http://u.720life.cn/g/90b70a0a9a080962cfe72b2f22b4c34664c8cc386a17c947ab2dacb28e4103cf)

 

It can convert *to*

 

  - `asciidoc` ([AsciiDoc](http://u.720life.cn/g/74b69af60b5ca88407dc8e6d65604791a4baf2bfe6e4c15f4b2e6f8c32aeae6c41b2ea6f6d21664bc4698ea50242783e) or
    `asciidoctor` ([AsciiDoctor](http://u.720life.cn/g/8ce75829b16e552d38f15156d98901686c366edd338ffdebf7ff81afd6251f17)
  - `beamer` ([LaTeX beamer](http://u.720life.cn/g/b4c5d8488d0fa6da4fb83cece8f5f6115b68898147a0ac3c3ad6c137da50c938) slide show)
  - `commonmark` ([CommonMark](http://u.720life.cn/g/6a3398b216073104d9b8e03a9a8bd6d74cffe559dde5d93acdcbc2eb636fa98f) Markdown)
  - `context` ([ConTeXt](http://u.720life.cn/g/d33365b902f7555c1a841a89dbf0471e370d9fe5dae223a09ee4b76ff5c77084)
  - `docbook` or `docbook4` ([DocBook](http://u.720life.cn/g/890ce3872016873bfc76c1e59963112abf0f3738fd32903977ddab66112446f2) 4)
  - `docbook5` (DocBook 5)
  - `docx` ([Word docx](http://u.720life.cn/g/dbf1195f8a53209e138d24666db06636e0c08fc9e8f56801f010d7db1f767118401a9d6660a8d5eeacc95ed29bc02797)
  - `dokuwiki` ([DokuWiki markup](http://u.720life.cn/g/bdefa628914765a0ba7e2e060ca080323d135b5c3b66a9f6a7796cbbfe4124efeca51501303051316b22010173dc892d)
  - `epub` or `epub3` ([EPUB](http://u.720life.cn/g/4e8e216fb28b4e0e354e4a3412be0e00c63cf2311edc33e01b0128c866cf80d2) v3 book)
  - `epub2` (EPUB v2)
  - `fb2`
    ([FictionBook2](http://u.720life.cn/g/b07ed9589153fc6334836a5769a49bd4d7ef39cad333ac14279a2a0074b5666828d6b154e78213b5bf444ad0034e84e97b9d8889c4772c4db0259a85bc26444484c3068f2eb725a923437b6f396201ed)
    e-book)
  - `gfm` ([GitHub-Flavored
    Markdown](http://u.720life.cn/g/1f425b0b33da40ebdfbaffd56fc94509ec09346c8015e0ae429751be8b3a78a5f9bd204a45e483731ccfaeb2b6a33217afd7e6c548399842104d2670e057aa31)
    or the deprecated and less accurate `markdown_github`; use
    [`markdown_github`](http://u.720life.cn/g/7a714ce062b52cc46cf9cbfa25cdbd19536c81a23f59226b9396bb48f1bcc9b1cf8c0ab74f00a4f87c291afec654824c)
    only if you need extensions not supported in
    [`gfm`](http://u.720life.cn/g/7a714ce062b52cc46cf9cbfa25cdbd19536c81a23f59226b9396bb48f1bcc9b1cf8c0ab74f00a4f87c291afec654824c).
  - `haddock` ([Haddock
    markup](http://u.720life.cn/g/aca3470af400f8736261e7011140fcbaa50dcb5b5965acf411421bc7c3a73b8f6e063893092db4cbef36bd1c5ecc70eefaa1f6c6293565912c1aad70d175a033)
  - `html` or `html5` ([HTML](http://u.720life.cn/g/098598e75704e07d68eba0aa885b4c2b22683595de7cca95118d75fdd21f2875),
    i.e. [HTML5](http://u.720life.cn/g/76fc2b13298a7e8ea26e6ca0b9ab2dd1bdd13ce9562bad5d2c2ae87f1aaa4e83)/XHTML [polyglot
    markup](http://u.720life.cn/g/098598e75704e07d68eba0aa885b4c2b76dc701dae92154610f5b49845d1a2a63899a5f67809bee8f4a00ed6c34a6110)
  - `html4` ([XHTML](http://u.720life.cn/g/098598e75704e07d68eba0aa885b4c2b42e86b73efbfd11a931735dcc9411e86) 1.0 Transitional)
  - `icml` ([InDesign
    ICML](http://u.720life.cn/g/59a9ebb18a9cf80290884f677eeccf107a41cafb95b5c51e775e771316b96c9abd28cee3af0fc0b7714b550358c5badffb0b174a2bca9bf0a65d9195707f34c51394a7491c0b4cd8ab1d7562c62c1c91bf3e49756e36e56eb529f17290942fee9cc6ad13b6ecb7c8591dd4d3e379a921)
  - `ipynb` ([Jupyter
    notebook](http://u.720life.cn/g/f11471ff78faf3759e63ff190304a656513b0c9887495a0b96725c7f59667f0fea5231cf0a3dc5708334e07e45dea1c2)
  - `jats_archiving` ([JATS](http://u.720life.cn/g/99459ac3d318804737729e83f1d31d7235e546408008542bfb98218805e1c287) XML, Archiving
    and Interchange Tag Set)
  - `jats_articleauthoring` ([JATS](http://u.720life.cn/g/99459ac3d318804737729e83f1d31d7235e546408008542bfb98218805e1c287) XML,
    Article Authoring Tag Set)
  - `jats_publishing` ([JATS](http://u.720life.cn/g/99459ac3d318804737729e83f1d31d7235e546408008542bfb98218805e1c287) XML, Journal
    Publishing Tag Set)
  - `jats` (alias for `jats_archiving`)
  - `jira`
    ([Jira](http://u.720life.cn/g/3b577f9c7a0abc5568a59f94744e84c7502b9c3aa8e45a3a1ef8343556cbf4e2552d5b4a119a977c2c270dd6988f249e1bc07a65d8f5e6f68570943cbbffbf746c725c2c68d935bb252e01c5d440823b)
    wiki markup)
  - `json` (JSON version of native AST)
  - `latex` ([LaTeX](http://u.720life.cn/g/75e2a56bd8dbabd4b75ca0fcf22ee7db782f8e859b4952d3a5bbe0a3b7a96526)
  - `man` ([roff man](http://u.720life.cn/g/f239eca7f6eff78ac365d5b3fd9a799b97444828250b15f2c3fb76b20af8765d)
  - `markdown` ([Pandoc’s
    Markdown](http://u.720life.cn/g/7a714ce062b52cc46cf9cbfa25cdbd19f4c212ad5314ebc63337eee86e223654132ce077d9c5f722b13df17cd6751d76)
  - `markdown_mmd`
    ([MultiMarkdown](http://u.720life.cn/g/9f447cda710f5e9f711b7a3fe65d92db3d142bd2fa0975258ce52fb840990c00fa922238f01d16bb66ab8a570f79fe3e)
  - `markdown_phpextra` ([PHP Markdown
    Extra](http://u.720life.cn/g/a00c9ad3254a6af90eef4e252f73e5fb88a1b58654cd0d87908304d72f3999cce54fd259ff8a93e1cf823e5eb0f0db17)
  - `markdown_strict` (original unextended
    [Markdown](http://u.720life.cn/g/82291fd6e6f08f28feb38b9e617d6f3a9555915fb522fb5acf99d58f231f63ba078746518ed17b3a0bcfeb2e955daf11)
  - `mediawiki` ([MediaWiki
    markup](http://u.720life.cn/g/33ae8636533afbeb23c2ec718d33e8304c62c0359ef5da336bac2eefc75de78e4e0654701c60ea884ceba14fc901763c)
  - `ms` ([roff ms](http://u.720life.cn/g/f239eca7f6eff78ac365d5b3fd9a799b1244f83bba7187ebcf5827781fef55e9)
  - `muse` ([Muse](http://u.720life.cn/g/c98f5b13222eb04fbe3598c1421bba53e1e12ea5e962a3795378e42a435c92c5368ac777e58d304ee4d5c3f5531a91bd)
  - `native` (native Haskell),
  - `odt` ([OpenOffice text
    document](http://u.720life.cn/g/dbf1195f8a53209e138d24666db06636d6f052b9892c039d27bffc03ce117ae4d559bcaf521591ec57af90d9dd536ae5)
  - `opml` ([OPML](http://u.720life.cn/g/2683720fe0af69b75cfe3ead25f73dd2f4f8b01c37200a31c2fdb40b0b4812ed)
  - `opendocument` ([OpenDocument](http://u.720life.cn/g/4712ca8d9ac4769f7b1cb5a85a124d193ae562b794ea89b3a07f55124e3710e8)
  - `org` ([Emacs Org mode](http://u.720life.cn/g/169b9a9f3410b0df5a61b092e133e6f711630f28ad8ed7544a5c1d13858c113f)
  - `pdf` ([PDF](http://u.720life.cn/g/e770f15eba029677661ba72944d728f7904a58438abac93ad853bd0128a351c5)
  - `plain` (plain text),
  - `pptx`
    ([PowerPoint](http://u.720life.cn/g/dbf1195f8a53209e138d24666db06636d0673e40b7d131d6cd345fad80f1287d663e821a353de38c148ee46d7e53bb43066665ade205b5d4fdb82d9465cd3e8e)
    slide show)
  - `rst`
    ([reStructuredText](http://u.720life.cn/g/dc1a85fb589ea64d06034278a19bb496f3a7ed283c801f6b11730ede23a17ffd4ce60d1830f2325e10acdd190be600f5699282955e71abbe7fed415486774d3f)
  - `rtf` ([Rich Text
    Format](http://u.720life.cn/g/dbf1195f8a53209e138d24666db066364814e21767556c0ead9c1468b6e47e07ad77c939a2166dd1c0d8ae9f3a62eef2)
  - `texinfo` ([GNU Texinfo](http://u.720life.cn/g/80aceec34af2d650b057d93ea119d365ad8ceb72709435e50e5bc4b244981c659832f95f559d707fdf2f26c60c61cb49)
  - `textile` ([Textile](http://u.720life.cn/g/b987cef77882ec082b3e6d0fe87b7c3728cd4a457a76732fb5eb0d3ae9d8e14d930f1bb1fff11899792b29a0f6f1c0cd)
  - `slideous` ([Slideous](http://u.720life.cn/g/7847756930fcef2800585a237d50bffa77ef1559a40d21f2c01836b5ce8b724df48c12bc257cc71a4d7a68e1c159f2e9) HTML
    and JavaScript slide show)
  - `slidy` ([Slidy](http://u.720life.cn/g/098598e75704e07d68eba0aa885b4c2bf1fca5665908df58c9d379d5d77459eda093bfac594831074c74e9998759aebe) HTML and
    JavaScript slide show)
  - `dzslides` ([DZSlides](http://u.720life.cn/g/5a041d7ac5de713097ccd14e70f1b3560172a7cb04348a610eaefa971469efaf) HTML5 +
    JavaScript slide show),
  - `revealjs` ([reveal.js](http://u.720life.cn/g/5b1515cf200d959be31d19175acdfd47760523d1191d5d1d3076e3150812559e) HTML5 + JavaScript
    slide show)
  - `s5` ([S5](http://u.720life.cn/g/577f5e569ec6b3c8ee1815a037f4043619824c6879fead8ec9874e56e7d3d1bc07b3481fdfbf05bf67d4eff08a97d2d8) HTML and JavaScript
    slide show)
  - `tei` ([TEI Simple](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304693fb6d40f267933be884a62f2611758c17a1bb6e70ab75f316820d02a4c65bf7)
  - `xwiki` ([XWiki
    markup](http://u.720life.cn/g/b36b2bc1536b2e80bf094dec9c7ffa3cd996dae0e1505ac461e2f586a9645f052f9a06c6e6d2f7f861cb23088fe6af9e40f346a2eb2952dea9feeceb06cc19b660c49fd443cf9c5c3bd1c2c2ba4f584d11ea77ff6294f3fa5d9ab24d3e36baf9)
  - `zimwiki` ([ZimWiki
    markup](http://u.720life.cn/g/44b9b24a68a9300a2a30170c52c6b02615bb3c6a32511be06e94a73b8ff7721f7c84cd1712c797ca7d8f1e9f28adcd8e6ed6b9a7792d15dc971b2d8128ab7b57)
  - the path of a custom Lua writer, see [Custom
    writers](http://u.720life.cn/g/7a714ce062b52cc46cf9cbfa25cdbd19a39a0c2f8a9bfad189ca87dd8d5f10566dafb2ecd5117fc30d8fc1b60a6a9cc3) below

 

Pandoc can also produce PDF output via LaTeX, Groff ms, or HTML.

Pandoc’s enhanced version of Markdown includes syntax for tables,
definition lists, metadata blocks, footnotes, citations, math, and much
more. See the User’s Manual below under [Pandoc’s
Markdown](http://u.720life.cn/g/7a714ce062b52cc46cf9cbfa25cdbd19f4c212ad5314ebc63337eee86e223654132ce077d9c5f722b13df17cd6751d76).

Pandoc has a modular design: it consists of a set of readers, which
parse text in a given format and produce a native representation of the
document (an *abstract syntax tree* or AST), and a set of writers, which
convert this native representation into a target format. Thus, adding an
input or output format requires only adding a reader or writer. Users
can also run custom pandoc filters to modify the intermediate AST (see
the documentation for [filters](http://u.720life.cn/g/7a714ce062b52cc46cf9cbfa25cdbd19bd0264be45de3f638b8417c59ac80947) and
[Lua filters](http://u.720life.cn/g/7a714ce062b52cc46cf9cbfa25cdbd19dcf9298d773481fe55a671a8cbedc2bc34ad63efcf92c32034dda84dea485f79)

Because pandoc’s intermediate representation of a document is less
expressive than many of the formats it converts between, one should not
expect perfect conversions between every format and every other. Pandoc
attempts to preserve the structural elements of a document, but not
formatting details such as margin size. And some document elements, such
as complex tables, may not fit into pandoc’s simple document model.
While conversions from pandoc’s Markdown to all formats aspire to be
perfect, conversions from formats more expressive than pandoc’s Markdown
can be expected to be lossy.

## Installing

Here’s [how to install pandoc](INSTALL.md).

## Documentation

Pandoc’s website contains a full [User’s
Guide](http://u.720life.cn/g/7a714ce062b52cc46cf9cbfa25cdbd196836d2d7862c69a0a08fdbe7e2dc22b0). It is also available
[here](MANUAL.txt) as pandoc-flavored Markdown. The website also
contains some [examples of the use of
pandoc](http://u.720life.cn/g/7a714ce062b52cc46cf9cbfa25cdbd19cd21e8c9781fed31c0877e5fe85269d5) and a limited [online
demo](http://u.720life.cn/g/7a714ce062b52cc46cf9cbfa25cdbd1974aa56124c0aa478779164d9f099bf10).

## Contributing

Pull requests, bug reports, and feature requests are welcome. Please
make sure to read [the contributor guidelines](CONTRIBUTING.md) before
opening a new issue.

## License

© 2006-2020 John MacFarlane (jgm@berkeley.edu). Released under the
[GPL](http://u.720life.cn/g/0faf03d8167674bee364b61e9b7d6858de092c730901b66e45ef02da10ec874db1e367d47d5a9a58a8e17fc8141f780b "GNU General Public License"),
version 2 or greater. This software carries no warranty of any kind.
(See COPYRIGHT for full copyright and warranty notices.)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea5e07e9a009cfe7f99a3ab79db8e4cd29f72d67ab8f9670abc3e9ef185b6dcc16e66206236215dbe8d0a3dcb89a51762)