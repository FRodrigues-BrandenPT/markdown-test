# Changelog

## [Unreleased](#unreleased)
 - ### Added
   - Changelog
 
 - ### Changed
   - In `SpotlessConfigExtension` the property `ktlintDataMap` is now `ktlintUserData`


## [1.0.0-RC1](#100-rc1---2021-04-02) - 2021-04-02
### Added
 - Application of the [SpotlessPlugin](https://github.com/diffplug/spotless/tree/main/plugin-gradle) if not applied in the Project
 - Configuration of the `SpotlessExtension`
 - For normal kotlin code it's used [diKtat](https://github.com/cqfn/diKTat)
 - For gradle kotlin scripts then it's used [ktlint](https://github.com/pinterest/ktlint)
 - Created an Extension with name `spotlessConfig` to personalize this configuration plugin
 - Within the SpotlessConfigExtension you can:
   - Change the `diktatVersion` with default [0.4.2](https://github.com/cqfn/diKTat/releases/tag/v0.4.2)
   - Change the `ktlintVersion` with default [0.41.0](https://github.com/pinterest/ktlint/releases/tag/0.41.0)
   - Add a different absolute path to the diKTat `diktat-analysis.yml` to `diktatConfigFile`
   - You can also change the [project properties](https://docs.gradle.org/current/dsl/org.gradle.api.Project.html#org.gradle.api.Project.properties) and add the `diktatConfigFile` absolute path there
   - Add a personalized `userData` to the `ktlintDataMap` with default being an empty map

### Changed 1.0.0-RC1
