**[[Terms_L2-Monolithic_Microservice_Archs|Overview L2]]** ----- [[Cloud 2 Monolithic and microservice Arch]]
[[Monolithic vs Microservices]]

> [!NOTE] **Monoliths:** Pros
> - Code in one place
> - Easier code debug
> - Can scale vertical or horizontal
> 	- **Horizontal:** Add another server
> 	- **Vertical:** Replace server with a more powerful one
> 
> Simple --> deployment topology(not much to deal with distributed components), dev workflow, monitoring, troubleshooting, testing. All code is in same place (code reuse is simple)
#### More pros
- Simple deployment topology, not much to deal with distributed components 
- Simple developer workflow 
- Simple monitoring 
- Simple troubleshooting 
- Simple testing 
- All the code is in the same place: code reuse is simple
# Notes

## Variants of Monolithic Architecture



### Single-process Monolith 
### Traditional Monolith
> [!tip] _they're not distributed...?_
> All have each their strengths depending on scale, purpose structure, etc.




> [!danger] **Monoliths:** Cons
> shit may be tangled together
> - New code has unexpected repercussions (spaghetti..?)
> - Need to understand the entire code base (new hires difficulty)
> - **Slow Tests**
> 	- Because of all the code (all has to be tested)

### Modular Monolith
- **Goal:** Increase modularity without increasing deployment units (containers etc.)
- Quicker tests
- Split into big modules
### Distributed Monolith



