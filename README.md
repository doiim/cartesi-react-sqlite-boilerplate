# Cartesi React Bootstrap Template

SQLite-based full-stack DApp template for React for quick and efficiently develop Cartesi integrated projects.

### Scope and Methodology

The idea is to create a template for create-react-app to facilitate kickstart projects. The template will use the last version of React and integration with Ethers to be able to send inputs to Sepolia Network and receive back notices from Cartesi Machine, that runs an app with a SQLite database. The inputs will be limited to serve as example for different interaction both on frontend and backend.

UML Diagrams related to the project will be created using Google Drawing and will be pasted on this readme markdown.

A demo of the project will be served at Github Pages and will allow any user that navigates to the app interact with SQLite database.

The completion and follow-up of the project would be able to be tracked using Github issues.

### Expected Deliverables

- A CRA Template to be easily initialized with a React Dapp as submodule.
- A React Dapp + Typescript fully integrated with Ethers.
- A Backend database Dapp managed by Cartesi machine, also running with Typescript.
- The app will also be served on github pages so user can check the demo before develop on top of it.

### Milestones and Timeline

- The project should took 2 weeks of work spammed on a range of 2 months starting by the day of grant confirmation.

### Team Details

- Filipe Montanari Soccol (Doiim CTO)
  - [Linkedin](https://www.linkedin.com/in/filipesoccol)
  - [GitHub](https://github.com/filipesoccol)

### Appendices

- https://github.com/cartesi/rollups-examples/tree/main/echo-js
- https://github.com/cartesi/rollups-deployment
- https://github.com/cartesi/rollups-contracts/tree/main/onchain/rollups/deployments

### Questions

- How SQLite maintain consistent running on Docker at Cartesi Machine?
- This [link](https://github.com/cartesi/rollups/tree/main/onchain/rollups/deployments) appear on multiple places during documentation, it should be updated to [this](https://github.com/cartesi/rollups-contracts/tree/main/onchain/rollups/deployments).

## Requirements for Grant

- Develop a SQLite-based full-stack DApp template.
- Integrate wallet functionality for Ethereum or compatible blockchains.
- Create a user-friendly and customizable frontend using React.
- Ensure ease of use and documentation suitable for junior developers including readme documentation, with an architecture diagram.
- Provide concise instructions for the deployment process.
- The template should include a feature to execute commands equivalent to those in the [frontend-console example](https://github.com/cartesi/rollups-examples/tree/main/frontend-console).
- Add your project to the Discord Spotlight channel and to [rolluplab.io](http://rolluplab.io)
- **GitHub repo must be licensed under the terms of the Apache 2.0
  open source license**
- Please note that a KYC process will be completed for the release of funding.
