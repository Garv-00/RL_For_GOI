# Getting Over It, played by reinforcement learning

Neural networks playing the real *Getting Over It with Bennett Foddy*, with one goal: be the first to finish it with
reinforcement learning, in one continuous climb from the bottom to the top with no save/load.

## How it works

- A C# plugin (BepInEx) runs inside the game and connects it to Python: physics advances in lockstep with the agent,
  and the whole game can be saved and restored exactly.
- PPO networks (Stable-Baselines3) train on 10 copies of the game at once, about 6,000 steps per second on one PC.
- A search with save/load found climbs through every part. Their states start the training of 28 networks, each
  specialized in one stretch of the route and chained along it.
- Continuous games from the bottom show where the networks get stuck, and those spots get targeted training.


## License

MIT. See [LICENSE](LICENSE).
