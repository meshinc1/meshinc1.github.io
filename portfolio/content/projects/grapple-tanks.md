+++
date = 2023-05-01T00:00:00-05:00
draft = false
title = 'Grapple Tanks Game'
company = 'Published Video Game'
duration = 'May 2023 - Present'
+++

# Grapple Tanks: Multiplayer Action Game :video_game:

***

### Introduction

Grapple Tanks is a 2D, online multiplayer fighter game playable with up to 4 people. Players manuever a grappling-hook-equipped tank in an endless deathmatch, where the last tank standing earns a point. Players have the option to play with friends, or to join public lobbies with random players.

My partner [Dorian Florescu](https://www.linkedin.com/in/florescu-dorian/) and I began toying with ideas for a game in our college apartment back in December 2021. It wasn't until mid-2023, however, that we committed to completing and publishing a playable video game.

Our goal with Grapple Tanks was to create a casual yet fast-paced and humerous game, with unique mechanics and extensive content for an engaging experience. Inspired by similar titles such as *Stick Fight: The Game*, we aimed to create a game that's intuitive to learn while still preserving some challenging aspects.

Our initial achievement involved creating a functional prototype for a multiplayer fighter game, incorporating fundamental physics-based movement and combat mechanics. By early October 2023, as the game approached a playable stage, we established an LLC named FlorMesh Games, enabling us to publish the game on [Steam](https://store.steampowered.com/app/2679340/Grapple_Tanks/).

Steam is a video game digital distribution service and storefront with 132 million monthly active users. The platform provides an intuitive solution for indie game developers seeking to publish their game and connect with a global audience.

In January 2024, we released Grapple Tanks as an early access (beta) title on Steam to begin building a community and gathering feedback from players. While we are continuing to expand the game's content, the publicly available version has the following features:

- **2-4 player** online multiplayer
- **10 levels**
- **Physics-based** grappling and combat
- **Dynamic terrain:** players can break through certain walls, floors, and ceilings
- **Weapons:** a variety of weapons made available through randomized supply drops
- **Powerups:** grant abilities including increased strength, agility, and damage protection

### Demo

To see Grapple Tanks in action with four players, check out the gameplay trailer below!

<!-- ![](https://www.youtube.com/watch?v=lcY4WZ8lxz0) -->
[![Grapple Tanks Gameplay Trailer](/images/projects/grapple-tanks-trailer.png)](https://www.youtube.com/watch?v=lcY4WZ8lxz0)
*Grapple Tanks gameplay trailer. Logos and artwork by [Noah Miller](https://noah85miller.myportfolio.com/)*.

### Technologies

**Languages:** C# \
**Technologies:** Unity game engine, Unity Netcode for GameObjects, Unity Cloud services, Steamworks

![](/images/projects/grapple-tanks-arch-white.png)

##### Design

Grapple Tanks is developed using the Unity game engine, leveraging its robust support for 2D game development and extensive built-in libraries. All runtime scripts are implemented in C#.

Players are connected via a peer-to-peer network, ensuring secure and reliable connections through Unity Relay. Netcode for GameObjects, a high-level networking library, facilitates the synchronization of data between players during matches.

A match consists of at least one host player and one-to-three connected client players. Matchmaking is handled through the Steamworks API, which uses a system built around the concept of a lobby.

##### Matchmaking Workflow

When initiating a match, a new Relay instance is allocated, with the player automatically assigned as the host. Utilizing the Steamworks API, a lobby is created, which can be configured as public or private. Steam lobbies serve as the platform for discovering active sessions, with the join-code for the Relay instance stored as metadata within the lobby.

Players can either join a friend's session or search for public sessions. In both cases, their client first locates and connects to a Steam lobby. Subsequently, the stored join-code is utilized to establish a connection to the Relay instance as a client.

### What's Ahead

As it currently stands, Grapple Tanks offers a fully playable experience and is (in my opinion) very entertaining to play with friends. However, it still falls short from the game Dorian and I envisioned when we began development. The primary area requiring attention is content expansion. To enhance the game's replayability, we are actively designing new levels, weapons featuring unique mechanics and physics, and environmental hazards, among other features.

In addition to content expansion, there are critical areas requiring improvement, particularly concerning network data synchronization. One of the significant challenges we've encountered revolves around mitigating conflicts arising from network latency. Hit registration, a common issue in multiplayer fighter games, exemplifies this challenge. The inherent latency between players can result in minor discrepancies in displayed player positions, which can escalate to critical discrepancies, such as missed hit registrations despite apparent hits.

Moving forward with the development of Grapple Tanks, our primary focus is to devise efficient solutions to address these network-related challenges, ensuring a fair and seamless experience for all players.

### Links
- [Gameplay Trailer](https://www.youtube.com/watch?v=lcY4WZ8lxz0)
- [Steam Page](https://store.steampowered.com/app/2679340/Grapple_Tanks/)
- [FlorMesh Games Website](https://flormeshgames.com/)
- [Stick Fight: The Game](https://landfall.se/stickfightthegame)
