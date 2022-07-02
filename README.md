# "Better OZ ERC721"

ERC721OZOptimized adds ERC721A-style data hitchhiking on to OpenZeppelin's ERC721 implementation.

ERC721OZOptimized limits token ids to uint64s (down from uint256s). Other than that, ERC721OZOptimized is functionally equivalent to OZ's implementation, but contains new functions to:

1. Show you per-address mint and burn stats:

- `_numberMinted(address owner)`
- `_numberBurned(address owner)`

2. Give you access to a uint64 of free address-level data:

- `_setAddressExtraData(address owner, uint64 extraData)`
- `_getAddressExtraData(address owner)`: 

3. Give you access to a uint96 of free token-level data:

- `_setTokenExtraData(uint tokenId, uint96 extraData)`
- `_getTokenExtraData(uint tokenId)`

## This is a proof of concept!

Other things you could do: add `unchecked` in various places. Add callbacks to set user / address data to save gas on double writes (like ERC721A). Test performance.
