npm install @openzeppelin/contracts


echo.> MyToken.sol


import "@openzeppelin/contracts/token/ERC20/ERC20.sol";


//kompajliranje 
truffle compile


//goerli test deploy

const HDWalletProvider = require('@truffle/hdwallet-provider');
require('dotenv').config();
const { MNEMONIC, PROJECT_ID } = process.env;

// ...

networks: {
  // ...
  goerli: {
    provider: () => new HDWalletProvider(MNEMONIC, `https://goerli.infura.io/v3/${PROJECT_ID}`),
    network_id: 5,       // Goerli's id
    confirmations: 2,    // # of confirmations to wait between deployments. (default: 0)
    timeoutBlocks: 200,  // # of blocks before a deployment times out  (minimum/default: 50)
    skipDryRun: true     // Skip dry run before migrations? (default: false for public nets )
  },
  // ...
}
