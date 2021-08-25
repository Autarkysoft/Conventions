In order to make reading the code and finding functions easy, everything is neatly categorized in all Autarkysoft projects.
This alongside concise names creates a clean structure.  
An example from `Bitcoin.Net` library:
```
Autarkysoft.Bitcoin
├ Blockchain
├─ Blocks
├── Block
├── BlockHeader
├ Cryptography
├── KeyDerivationFunctions
├─── PBKDF2
├─── Scrypt
├── IRandomNumberGenerator
├── StrongRandom
├── WeakRandom
```
For projects with a user interface the MVVM pattern is used. In this structure:  
* Models, views and view models are placed in their own folders (as opposed to separate projects).
* The actual work is usually performed by classes placed in Services folder and injected as a dependency in view models.
* We try not to use MVVM libraries!
