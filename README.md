# Changelog

## [Unreleased](#unreleased)
### Added
 - Changelog
### Changed
 - In `SpotlessConfigExtension` the property `ktlintDataMap` is now `ktlintUserData`
### Fixed
- Only try to find and/or generate the diKTat yaml if there's no path defined in `diktatConfigFile`

## [1.0.0-RC1](#100-rc1---2021-04-02) - 2021-04-02
### Added <small>1.0.0-RC1</small>
 - Application of the [SpotlessPlugin](https://github.com/diffplug/spotless/tree/main/plugin-gradle) if not applied in the Project
 - Configuration of the `SpotlessExtension`
 - For normal kotlin code it's used [diKtat](https://github.com/cqfn/diKTat)
 - For gradle kotlin scripts then it's used [ktlint](https://github.com/pinterest/ktlint)
 - Small custom format for `.gitignore`, `properties`, `toml`, and `yaml` files that removes trailing whitespaces and always add a newline in the end of the file
 - Created an Extension with name `spotlessConfig` to personalize this configuration plugin
 - Within the SpotlessConfigExtension you can:
   - Change the `diktatVersion` with default [0.4.2](https://github.com/cqfn/diKTat/releases/tag/v0.4.2)
   - Change the `ktlintVersion` with default [0.41.0](https://github.com/pinterest/ktlint/releases/tag/0.41.0)
   - Add a different absolute path to the diKTat `diktat-analysis.yml` to `diktatConfigFile`
   - You can also change the [project properties](https://docs.gradle.org/current/dsl/org.gradle.api.Project.html#org.gradle.api.Project.properties) and add the `diktatConfigFile` absolute path there
   - Add a personalized `userData` to the `ktlintDataMap` with default being an empty map
 - Generates a `diktat-analysis.yml` file in `config/diktat` in the most upper project if there's none with the following contents:
   ```yaml
   # Common configuration
   - name: DIKTAT_COMMON
     configuration:
     # put your package name here - it will be autofixed and checked
     domainName: pt.branden.brandenportal
     testDirs: test
     kotlinVersion: 1.4
   - name: HEADER_MISSING_OR_WRONG_COPYRIGHT
     enabled: false
   ```
