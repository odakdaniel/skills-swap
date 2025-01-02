# Skill Exchange System

## Overview

The **Skill Exchange System** is a decentralized platform that enables users to exchange skills, collaborate, and learn from one another. Built using Rust and the Internet Computer (ICP) framework, this project provides a robust backend for managing users, skills, offers, matches, achievements, and more.

## Features

- **User Management**:
  - Register and manage users with unique `Principal` identifiers.
  - Track user statistics, teaching/learning streaks, achievements, and reputation scores.

- **Skill Management**:
  - Add, endorse, and verify skills.
  - Manage skill levels (Beginner to Master) and track mastery points.

- **Skill Exchange**:
  - Create, view, and accept skill exchange offers.
  - Manage the lifecycle of exchanges: active, matched, and completed.

- **Achievements**:
  - Earn achievements for milestones like the first exchange, consistent learning, and high ratings.
  - Visualize progress with points and badges.

- **Statistics Dashboard**:
  - System-wide insights, including total users, skills, and exchanges.
  - Track the highest-rated users and other key metrics.

- **Secure and Decentralized**:
  - Leverages the Internet Computer for scalable, decentralized storage and computation.

## Technologies Used

- **Language**: Rust
- **Framework**: Internet Computer (ICP)
- **Data Storage**: Stable BTreeMap with `ic_stable_structures`
- **Serialization**: Candid and Serde
- **Thread-local Memory Management**: `MemoryManager`

## Prerequisites

To run this project, ensure you have the following installed:

- [Rust](https://www.rust-lang.org/) (latest stable version)
- [DFX](https://internetcomputer.org/docs/current/developer-docs/quickstart/dfx-quickstart) (Internet Computer SDK)
- [Node.js](https://nodejs.org/) (for managing frontend, if applicable)

## Installation and Setup

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/odakdaniel/skills-swap.git
   cd skills-swap
   ```

2. **Install Dependencies**:
   - Install Rust dependencies:
     ```bash
     cargo build
     ```
   - Install DFX:
     Follow the [official DFX installation guide](https://internetcomputer.org/docs/current/developer-docs/quickstart/dfx-quickstart).

3. **Start the Internet Computer Local Replica**:
   ```bash
   dfx start --background --clean
   ```

4. **Deploy the Canister**:
   ```bash
   npm run gen-deploy
   ```

5. **Verify Deployment**:
   After deployment, the system will generate a canister ID. Use this ID to interact with the system.

## Usage

### API Endpoints

The system exposes the following API endpoints (via Candid interface):

#### User Operations
- `create_user(payload: CreateUserPayload) -> Result<User, Message>`
- `get_user_by_id(user_id: u64) -> Result<User, Message>`
- `get_user_by_owner() -> Result<User, String>`

#### Skill Operations
- `add_skill(payload: AddSkillPayload) -> Result<Skill, Message>`
- `endorse_skill(payload: EndorseSkillPayload) -> Result<String, Message>`

#### Offer Management
- `create_offer(payload: CreateOfferPayload) -> Result<SkillOffer, Message>`
- `accept_offer(payload: AcceptOfferPayload) -> Result<Match, Message>`

#### Lesson Management
- `complete_lesson(payload: CompleteLessonPayload) -> Result<String, Message>`

### Deployment Notes
- The system is designed to run on the Internet Computer.
- For local testing, use `dfx` to manage the replica and deploy canisters.

## Contributing

Contributions are welcome! If you'd like to contribute, please:

1. Fork the repository.
2. Create a new branch for your feature or bugfix.
3. Submit a pull request with a detailed description of your changes.

## License

This project is licensed under the MIT License. See the LICENSE file for more information.

---

**Enjoy using the Skill Exchange System! If you have any questions or feedback, feel free to reach out.**

