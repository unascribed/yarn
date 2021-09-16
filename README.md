# Una's Yarn
![Latest version](https://img.shields.io/maven-metadata/v?color=%2300dbad&metadataUrl=https%3A%2F%2Frepo.unascribed.com%2Fcom%2Funascribed%2Fyarn%2Fmaven-metadata.xml)

A personal fork of Yarn for 1.16.5. See [FabricMC/yarn](https://github.com/FabricMC/yarn) for more info about what Yarn is.

## Usage

Are you stubbornly staying 1.16.5 as well, but you want some of the newer mappings and random fixes?

1. Add my repo to your repositories in build.gradle: `maven { url 'https://repo.unascribed.com' }`
2. Run `./gradlew migrateMappings --mappings com.unascribed:yarn:1.16.5-una+build.2:v2 --output src/main/java`
3. Change `net.fabricmc:yarn` in your build.gradle's `mappings` dependency to `com.unascribed:yarn`
4. Run `./gradlew genSources` to update your source/javadoc jar
5. Congratulations, you're using this Yarn fork.
