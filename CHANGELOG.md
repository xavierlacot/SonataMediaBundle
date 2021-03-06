# Change Log
All notable changes to this project will be documented in this file.
This project adheres to [Semantic Versioning](http://semver.org/).

## [3.5.0](https://github.com/sonata-project/SonataMediaBundle/compare/3.4.0...3.5.0) - 2017-03-08
### Fixed
- Optional dependency to SonataFormatterBundle is now on `^3.2`
- Fixed issue when using SonataMediaBundle blocks in conjunction with SonataPageBundle and page composer (Sonata sandbox)
- Double padding on media list

### Removed
- Removed an ugly hack to retrieve configuration on `AddProviderCompilerPass`

## [3.4.0](https://github.com/sonata-project/SonataMediaBundle/compare/3.3.1...3.4.0) - 2017-02-28
### Added
- An icon to admin menu (fa-image)
- Added `getRequest` method on controller for BC with Symfony 2.3+
- Added test on `MediaAdminController`

### Changed
- Replaced form types for the FQCN's

### Fixed
- Support for Twig 2.0
- Callback contraint is not a valid callable on Symfony 3
- `BaseAdmin` incorrectly retrieved `providerName`
- Fixed BlockBundle deprecation messages
- Fixed pager test with DatagridBundle 2.2.1
- Media List is now filterable by Category again
- Incorrect access to providerName parameter in request in `Admin/BaseMediaAdmin.php`
- Wrong FQCN's and added missing end() on GalleryAdmin
- Calling a macro without importing it is an error on twig 2.0
- Remove deprecations from non FQCNs on form types on `MediaAdmin`

### Removed
- `cascade_validation` from `GalleryAdmin`
- ClassificationBundle is now an optional dependency

## [3.3.1](https://github.com/sonata-project/SonataMediaBundle/compare/3.3.0...3.3.1) - 2017-02-02
### Added
- Added filesize check to upload
- Added empty filename check to upload
- Generate thumbnails asynchronously if creating Media on console commands.

### Changed
- translation in twig templates now uses the twig translation filter
- Moved ApiDoc groups from string to array.

### Fixed
- Deprecation warning for `addDownloadSecurity`
- Moved FosRest groups from string to array and reimplemented the orderBy parameter enabling support for FosRestBundle>=2.0.
- Missing italian translations

## [3.3.0](https://github.com/sonata-project/SonataMediaBundle/compare/3.2.0...3.3.0) - 2016-09-08
### Added
- Added config key to define default resizer
- Added config key to define default resizer adapter

### Fixed
- The `provider` and `context` options are now required
- Use `$request` instead of  `$this->get('request')`

### Removed
- Ability to provide custom attributes for a thumbnail

## [3.2.0](https://github.com/sonata-project/SonataMediaBundle/compare/3.1.0...3.2.0) - 2016-08-18
### Added
- Created `getReferenceUrl` method for all video providers
- Add parameter to specify aws_sdk version

### Changed
- Allow `knplabs/gaufrette` `^0.2`
- Update configuration and metadatabuilder to comply with AWS SDK 3.x

### Fixed
- Fixed wrong block inheritance in edit template
- Fixed wrong html usage in edit template
- Fixed loop in `Pool::getDownloadSecurity`
- Fixed deprecated call of `downloadSecurity` in `Resources/views/MediaAdmin/edit.html.twig` template.

## [3.1.0](https://github.com/sonata-project/SonataMediaBundle/compare/3.0.0...3.1.0) - 2016-07-22
### Added
- Added `Sonata\MediaBundle\Listener\ORM\MediaEventSubscriber::onClear` to clear the `rootCategories` cache when the EntityManager is cleared
- Added `region` key to S3Client config
- Added `alt` attribute to thumbnail twig tag

### Changed
- Injection of `Session` instead of the whole `Container` in `Security/SessionDownloadStrategy`
- `Sonata\MediaBundle\Listener\ORM\MediaEventSubscriber::onClear` now subscribes to `onClear` too

### Deprecated
- `$container` property in `Security/SessionDownloadStrategy`
- Deprecated `Pool::$downloadSecurities` for `Pool::$downloadStrategies` property
- Deprecated `Pool::addDownloadSecurity` for `Pool::addDownloadStrategy` method
- Deprecated `Pool::getDownloadSecurity` for `Pool::getDownloadStrategy` method

### Fixed
- Restored `ApiDoc` and `QueryParam` use statements in `Api/GalleryController`
- Added missing `sonata-project/block-bundle` dependency
- Fixed media widget spanish translations
- Support for FOSRestBundle 2.0
- Fixed `ApiMediaType::getParent` compatibility with Symfony3 forms
- Fixed `MediaType::buildForm` compatibility with Symfony3 forms
- Fixed `MediaType::getParent` compatibility with Symfony3 forms
- Fixed `BaseVideoProvider::buildEditForm` compatibility with Symfony3 forms
- Fixed `BaseVideoProvider::buildCreateForm` compatibility with Symfony3 forms
- Fixed `BaseVideoProvider:: buildMediaType` compatibility with Symfony3 forms
- Fixed `FileProvider::buildEditForm` compatibility with Symfony3 forms
- Fixed `FileProvider::buildCreateForm` compatibility with Symfony3 forms
- Fixed `FileProvider::buildMediaType` compatibility with Symfony3 forms
- Fixed mixed-content error when loading Pixlr editor under https
- Gaufrette compatibility with Symfony 3
- Fix deprecated usage of `Admin` class
- Added missing `BaseProvider::$name` property
- Removed double translation in gallery edit form
- Reuse of root categories instances after the entity manager has been cleared

### Removed
- Internal test classes are now excluded from the autoloader
