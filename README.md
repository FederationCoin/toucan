# Toucan

Java LifeHash visualization used by Federation Sparrow. You do not install or run this tree by itself.

Not affiliated with Sparrow Wallet. Experimental. No warranty; see the [Apache 2.0 license](LICENSE).

## For users

Federation Sparrow may show a LifeHash image for keys or payloads. There is no separate Toucan app and no Maven install for this fork.

## For developers

Forked from [sparrowwallet/toucan](https://github.com/sparrowwallet/toucan) (port of [bc-lifehash](https://github.com/BlockchainCommons/bc-lifehash)). Origin is `git@github.com:FederationCoin/toucan.git`. Mainline is `federationcoin`. GitHub is detached from that fork; **never push** sparrowwallet.

Java `group` remains `com.sparrowwallet`. Do **not** add `implementation('com.sparrowwallet:toucan:…')` from Maven Central. `maven.federationcoin.org` is not provisioned. Sparrow builds this git submodule from source. Minimum Java 17 for this library; Federation Sparrow itself needs Java 25.

### Clone and build

```bash
git clone git@github.com:FederationCoin/toucan.git
git checkout federationcoin
./gradlew jar
./gradlew test
```

```java
import com.sparrowwallet.toucan.*;
import java.awt.image.BufferedImage;

LifeHash.Image lifeHashImage = LifeHash.makeFromUTF8("Hello World", LifeHashVersion.VERSION2, 1, false);
BufferedImage awtImage = LifeHash.getBufferedImage(lifeHashImage);
```

No extra runtime dependencies.

### Branching

Work on a branch off `federationcoin`. Open a same-repo pull request; a human merges. Do not push straight to mainline. This library has no `get-to-mainnet` branch this iteration.

### Release

Independent versions and git tags come later. Sparrow pins a gitlink SHA that must already be on origin `federationcoin`. No Maven publish.

### Quality

Code quality checks and metrics will be added over time.
