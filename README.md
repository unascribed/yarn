# Una's Yarn
![Latest version](https://img.shields.io/maven-metadata/v?color=%2300dbad&metadataUrl=https%3A%2F%2Frepo.unascribed.com%2Fcom%2Funascribed%2Fyarn%2Fmaven-metadata.xml)

A personal fork of Yarn for 1.16.5. See [FabricMC/yarn](https://github.com/FabricMC/yarn) for more info about what Yarn is.

## Usage

Are you stubbornly staying 1.16.5 as well, but you want some of the newer mappings and random fixes?

1. Add my repo to your repositories in build.gradle: `maven { url 'https://repo.unascribed.com' }`
2. Run `./gradlew migrateMappings --mappings com.unascribed:yarn:1.16.5-una+build.2:v2 --output src/main/java` - change the version as necessary to the current latest (see the above badge)
3. Change `net.fabricmc:yarn` in your build.gradle's `mappings` dependency to `com.unascribed:yarn`
4. Update your gradle.properties or build.gradle to change the mappings version to the current latest (see the above badge)
5. Run `./gradlew genSources` to update your source/javadoc jar
6. Congratulations, you're using this Yarn fork.

## Current Changes

* Entity::collides → occludesRaycasts
  * This method name is misleading, and overlaps with isCollidable. The new name better matches what the method affects.
  * Also added a Javadoc for extra clarity.
* Entity::isCollidable → hasHardCollision
  * This method name is misleading, and overlaps with collides. The new name better matches what the method affects.
  * Also added a Javadoc for extra clarity.
* Entity#field_25599 → currentSubmergedFluid
* LivingEntity#knockbackVelocity → attackerYaw
  * This field name is just plain wrong. It's the "attacker yaw" field that affects view damage tilt that doesn't sync from the server in vanilla.
  * There is a related fix in Fabrication: [Sync Attacker Yaw](https://unascribed.com/fabrication/#fixes.sync_attacker_yaw).
* Merged LambdAurora's NBT refactor
  * All of the NBT classes now end with "Nbt" instead of "Tag".
    * This fixes them conflicting with the registry Tag facility.
  * All of the NBT classes are now documented.
  * Various other NBT-related cleanups.
