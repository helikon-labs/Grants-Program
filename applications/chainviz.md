# ChainViz v1

- **Team Name:** Helikon Labs
- **Payment Address:** `bc1qxjy7sw0ffvpq86t6hj3mmqhnfz2hxt6pk7zdz0` (BTC)
- **Level:** 🐤 2

## Project Overview :page_facing_up:

### Overview

ChainViz Alpha web application, available at [alpha.chainviz.app](https://alpha.chainviz.app), is an [open-source](https://github.com/helikon-labs/chainviz) real-time 3D visualization of the Kusama relay chain block production process.

![](https://raw.githubusercontent.com/helikon-labs/chainviz/development/readme_files/screenshot_01.png)

Application in its current alpha version provides the following features:

- 3D visualization of:
  - Active validators, including paravalidation indication
  - Block production by validators
  - Block finalization
- Navigation of the 3D scene through zooming, panning and rotation
- Network status display
- Active validator list and search over identity/address
- Validator details panel upon click on a validator in the 3D model, or the validator list

**This application is to fund the building of the first major version of ChainViz**, with the following features/visualizations:

- Complete professional redesign of the application
- Additional support for Polkadot
- Parachains
  - Assigned paravalidators
  - XCM messages between parachains, or from parachains to relay chains
- Block content on click
  - Extrinsics
  - Events
- Generative sound effects for:
  - Background sound
  - Block production and finalization
  - XCM messages
  - Session and era changes

With these additional features, ChainViz is going to become a **complete real-time visualization** of the Polkadot and Kusama relay chains and their parachains.

### Project Details

#### System Architecture

ChainViz Alpha currently utilizes both [SubVT backend services](https://github.com/helikon-labs/subvt-backend) for Kusama and Polkadot JS API as follows.

- SubVT active validator list [service](https://github.com/helikon-labs/subvt-backend/tree/development/subvt-validator-list-server)
  - List of all active validators
  - For each validator, a summary including:
    - Identity
    - Preferences
    - Self stake
    - Nomination count and total amount,
    - 1KV data if exists
    - and more
- SubVT network status [service](https://github.com/helikon-labs/subvt-backend/tree/development/subvt-network-status-server)
  - Era index
  - Era reward points
  - Total, minimum, maximum and average stake amounts
- Polkadot JS API
  - Finalized block header subscription
    - Utilized to mark finalized blocks
  - Best block header subscription
    - Utilized to display the block production animation
    - Identify uncle blocks and visualize them

ChainViz Alpha system architecture can be illustrated as follows.

<p align="center">
	<img width="400" src="https://raw.githubusercontent.com/helikon-labs/Grants-Program/helikon-chainviz-application/applications/chainviz-files/01-chainviz_alpha_system_architecture.png">
</p>

Proposed upgrade to the first major version requires the following additional data:
- Block details
  - Extrinsic list and parameters
    - XCM messages
  - Event list and parameters
- Validator details

Upgraded system architecture can be illustrated as follows, newly added components are colored in yellow:

<p align="center">
	<img width="600" src="https://raw.githubusercontent.com/helikon-labs/Grants-Program/helikon-chainviz-application/applications/chainviz-files/02-chainviz_v1_system_architecture.png">
</p>

Upgraded system utilizes the to-be-developed SubVT Block Details Service to access the block content, and the existing SubVT Validator Details Service for any necessary validator data that is not available through the validator list service.

#### Redesign

TBD

#### Audio Development

ChainViz is going to have an internal audio synthesizer, using the Web Audio API through [Pizzicato](https://github.com/alemangui/pizzicato) or a similar module, that generates parameterized audio for:

- Background
  - Parameterized by blockchain state
- Block production
- XCM messages
- Offline offences
- Era and epoch changes

Please view [ChainSynth Alpha](https://alpha.chainsynth.app) for a similar effort by us. You may find information on how the sound is generated in the [ChainSynth repository](https://github.com/helikon-labs/chainsynth) readme.

### Ecosystem Fit

There is currently no direct match in the Dotsama ecosystem of the features offered by ChainViz. ChainViz Alpha got [shared on Twitter](https://twitter.com/gavofyork/status/1491480880245874708) by Dr. Gavin Wood upon initial release, and received a lot of praise from various Dotsama ecosystem members.

<p align="center">
	<img width="400" src="https://raw.githubusercontent.com/helikon-labs/Grants-Program/helikon-chainviz-application/applications/chainviz-files/03-chainviz_alpha_gavin_wood_twitter.png">
</p>

There are currently two other projects that visualize certain aspects of the Dotsama blockspace:
1. [Kusamaverse by Odyssey](https://odyssey.org/kusamaverse), which is closer to a metaverse space for Kusama, focused more on the interaction of the actors in the ecosystem.
2. [XCM Dashboard](https://polkadot.subscan.io/xcm_dashboard) by the Subscan team, which is a visualization of the cross-chain messaging channels between parachains.

ChainViz is unique in that it focuses on a very clear real-time visualization of the internals of the Dotsama machine. As we're going to explain in the Future Plans section, it also has the potential to have educational, entertainment and functional value through future development.

## Team :busts_in_silhouette:

### Team members

- **Team Lead & Main Developer:** Kutsal Kaan Bilgin
- **Project Manager:** Ugur Becer
- **TBD:** Egor Zmaznev
- **TBD:** Daria Kravchenko
- **Rest of the Design Team:** -

### Contact

- **Contact Name:** Kutsal Kaan Bilgin
- **Contact Email:** kutsal@helikon.io
- **Website:** [helikon.io](https://helikon.io)

### Legal Structure

- **Registered Address:** Omer Avni Mah. Balcik Sok. 4/4 34427 Beyoglu Istanbul Turkey
- **Registered Legal Entity:** Helikon Teknoloji ve Medya Tic. Ltd. Sti.

### Team's experience

#### Helikon Labs

A crypto-native software development company based in Istanbul. Founded by [Kutsal Kaan Bilgin](https://github.com/kukabi), Helikon Labs got introduced into the Dotsama ecosystem in January 2021. Currently focused on validator tooling, infrastructure support and creative coding projects for the Dotsama ecosystem.
- Received a Kusama treasury grant ([M1-3](https://kusama.polkassembly.io/treasury/99), [M4-5](https://kusama.polkassembly.io/treasury/129)) for:
  - Completed
    - [SubVT Backend](https://github.com/helikon-labs/subvt-backend)
    - [SubVT Data Swift](https://github.com/helikon-labs/subvt-data-swift)
    - [SubVT Data Android](https://github.com/helikon-labs/subvt-data-android)
  - Alpha Testing
    - [SubVT iOS](https://github.com/helikon-labs/subvt-ios)
  - Under Development
    - [SubVT Android](https://github.com/helikon-labs/subvt-ios)
- [Received](https://github.com/w3f/Grants-Program/blob/master/applications/subvt-telegram-bot.md) and [delivered](https://github.com/w3f/Grant-Milestone-Delivery/blob/master/deliveries/subvt_telegram_bot-milestones-1-and-2.md) a W3F Level-1 Open Grant for the [SubVT Telegram Bot](https://github.com/helikon-labs/subvt-backend/tree/development/subvt-telegram-bot) for [Kusama](https://t.me/subvt_kusama_bot) and [Polkadot](https://t.me/subvt_polkadot_bot).
- Member of both Polkadot and Kusama Thousand Validators programs.
- Running two Kusama validators, and one Polkadot validator.
- Active governance participation.

#### Kutsal Kaan Bilgin

Founder of Helikon Labs. Software developer with a bachelor's degree in Computer Science and 20 years of experience in development and leading software development projects in diverse fields such as fintech, defense industry, art installations and GIS. Focusing on user-friendly, aesthetically pleasing and creative blockchain application development since late 2019. Dotsama native since early 2021. Developer of SubVT (please see above), [ChainViz Alpha](https://alpha.chainviz.app) and [ChainSynth Alpha](https://alpha.chainsynth.app). Guest to a Substrate Seminar [episode](https://www.youtube.com/watch?v=e-o_hTj3UFk&t=6119s&ab_channel=ParityTech) on blockchain UI application development.

#### Ugur Becer

Cofounder of  [XOVR](https://www.xovr.co). Ugur comes from a [background of cinematography](https://www.ugurbecer.com) who holds a MFA degree from NYFA. Many films he worked on were selected and awarded for prestigious film festivals including Toronto Film Festival, London Film Festival and Istanbul film Festival.  He has also been selected as a member of [‘Berlinale Talent’](https://www.berlinale-talents.de/bt//talent/ugur-becer/profile) as a cinematographer.
In 2015 he started focusing on cinematic immersive experiences which led him to opening his Virtual Reality Production Studio called XOVR.
He has created over 30 VR projects in 7 years - to high profile clients- and served as Project Manager to all of them. The last 2 VR projects were supported and granted from World Bank and European Union. They were all highly accomplished and successfully delivered. Ugur is now very excited to focus on blockchain technologies and Helikon projects on dotsama ecosystem.

#### Egor Zmaznev

TBD

#### Daria Kravchenko

TBD

#### Rest of the Design Team

TBD


### Team Code Repos

- [Helikon Labs](https://github.com/helikon-labs)
  - [ChainViz](github.com/helikon-labs/chainviz)
  - [ChainSynth](github.com/helikon-labs/chainsynth)
  - [SubVT Backend](github.com/helikon-labs/subvt-backend)
  - [SubVT iOS](github.com/helikon-labs/subvt-ios)
  - [SubVT Android](github.com/helikon-labs/subvt-android)
  - [SubVT Data - Swift](github.com/helikon-labs/subvt-data-swift)
  - [SubVT Data - Android](github.com/helikon-labs/subvt-data-android)
- Team Members
  - Kutsal Kaan Bilgin [https://github.com/kukabi](https://github.com/kukabi)

### Team LinkedIn Profiles

TBD

### Team Behance Profiles

TBD

## Development Status :open_book:

Alpha version of ChainViz has been live since February 2022 as detailed under the Project Details section. There hasn't been any development for the first major version proposed by this document.

## Development Roadmap :nut_and_bolt:

### Overview

- **Total Estimated Duration:** 3 months
- **Full-Time Equivalent (FTE):**  0.33
- **Total Costs:** 30,000 USD

### Milestone 1 — Backend Development, UI/UX Design

- **Estimated duration:** 1 month
- **FTE:**  0.33
- **Costs:** 10,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | GPLv3 |
| 0b. | Documentation | Milestone progress report and inline code documentation. GitHub README that explains how to run an instance. |
| 0c. | Testing Guide | Separate markdown in the GitHub repository that documents the complete backend test cases and how to run them. |
| 0d. | Docker | Necessary Docker/compose files necessary to run the backend services. |
| 0e. | Video Article | A YouTube video accompanied by an article on Helikon website or another blog site that documents the milestone development/design process and the outcome. |
| 1. | UI and UX Design Output | Complete design output on Figma, and other design assets uploaded to the project repository. |
| 2. | Backend Services | Required backend services coded and ready to test in the SubVT repository. |

### Milestone 2 - Audio Design, Application Development

- **Estimated Duration:** 2.0 months
- **FTE:**  0.33
- **Costs:** 20,000 USD

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | GPLv3 |
| 0b. | Documentation | Milestone progress report and inline code documentation. GitHub README that explains how to run an instance. |
| 0c. | Testing Guide | Separate markdown in the GitHub repository that documents the complete test cases and how to run them. |
| 0d. | Docker | Necessary Docker/compose files necessary to run the backend services and the ChainViz web application. |
| 0e. | Video Article | A YouTube video accompanied by an article on Helikon website or another blog site that documents the milestone development/design process and the outcome. |
| 1. | Web Application | Complete web application live at [chainviz.app](https://chainviz.app), and the complete source code in the project repositories. |

## Future Plans

- Add educational components.
  - Replayable voice recordings attached to the various components and processes for the users who would like to learn more about the internals of the Dotsama machine.
  - Text and visual augmentation
- Validator spaces and staking through ChainViz.
-  iOS and Android phone, table and watch applications.
-  Exploration of VR and AR possibilities.

## Additional Information :heavy_plus_sign:

**How did you hear about the Grants Program?**

We have successfully [delivered](https://github.com/w3f/Grant-Milestone-Delivery/blob/master/deliveries/subvt_telegram_bot-milestones-1-and-2.md) a W3F Level-1 Open Grant. Please view the [application document](https://github.com/w3f/Grants-Program/blob/master/applications/subvt-telegram-bot.md) for the details of our first introduction to the Grants Program.
