# Collection of token lists used by the Bloomium DEX

Token Lists is a specification for lists of token metadata (e.g. address, decimals, etc.) that can be used by any dApp
interfaces that needs one or more lists of tokens. Anyone can create and maintain a token list, as long as they follow
the specification. The Bloomium community invites you to add your token to our tokenlists!


## Adding Your Token to an Existing List


### General Requirements
1. Token should be verified on the explorer of that chain.
2. Token must be added to the list of the network it belongs to.


## Adding Your Token
1. Add an entry in the `tokens` field of the appropriate tokenlist. Here is an example using OCEAN from Ocean Protocol:
2. Add the below `JSON` struct to the `evm-lists/avalanche.json` file.
    ```json
    {
        "address": "0x0057371Cd534577b6040E140654DE0958116Cf3A",
        "chainId": 43114,
        "name": "Ocean Protocol",
        "symbol": "OCEAN",
        "decimals": 18,
        "logoURI": "https://raw.githubusercontent.com/Bloomium/bloomium-token-lists/main/evm-logos/avalanche/0x0057371Cd534577b6040E140654DE0958116Cf3A/logo.png"
    }
    ```
3. Update the `timestamp` field to the current timestamp.
4. Update the `version` field to adhere to semantic versioning:

    * Increment major version when tokens are removed
    * Increment minor version when tokens are added
    * Increment patch version when tokens already on the list have minor details changed (name, symbol, logo URL, decimals)

    ***Note:*** Changing a token address or chain ID is considered both a remove and an add, and should be a major version update.
5. You must add the token logo by going to the folder `evm-logos` under the correct chain e.g `avalanche` and create a new folder with the name of the token address e.g `0x0057371Cd534577b6040E140654DE0958116Cf3A` and add the logo of the token there under the name `logo.png`.
6. Ensure that the logo is 256 pixels in width and 256 pixels in height.
7. Create a Pull Request with your addition and after the Bloomium team has reviewed that it has met all the criteria it will be merged.
