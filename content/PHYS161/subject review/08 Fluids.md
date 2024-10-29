# Fluid Mechanics (from physics 2 notes)

## Causes of Pressure in a Fluid

- **Fluid** - anything that flows
    - Gases and liquids both have fluid behavior
    - In AP Physics 2, we assume the fluid is idealized (frictionless and incompressible)

1. **Pressure due to Thermal Motion**
    1. Fluids are made up of many vibrating molecules
        1. The greater the thermal energy of a fluid, the faster the molecules will vibrate
    2. Molecules collide with surfaces surrounding the fluid, exerting forces
        1. Forces parallel to the wall of a container cancel out
        2. Forces perpendicular to the wall of a container do NOT cancel out and cause fluid pressure perpendicular to container walls
2. **Pressure due to Gravity**
    1. At Point B at a greater depth than Point A in a fluid, the pressure due to gravity is greater because there are more molecules to hold up

- The thermal effect and gravitational effect in fluids combine to create overall pressure in a fluid
- Gases typically have a smaller gravitational effect than liquids as they have a smaller density

## Density

- ρ = m/V
    - ρ = density (called rho)
    - m = mass
    - V = volume
    - In AP Physics 2, density is typically measured in kg/m^3
    - Water density is 1000 kg/m^3
- Manipulation of the density equation:
    - m = ρV
    - When discussing the weight of a fluid, the typical formula of F = mg can be rewritten as F = ρVg where g is the gravitational constant

## Static Fluids

- Static Fluid: a still fluid
    
- Pressure = force per unit of area
    
- P = F/A
    
    - F = Force due to pressure
    - A = total area of contact (typically between a fluid and an object)
    - measured in Pascals (Pa) which is also Newtons per meter squared
- Pressure will typically be presented in two ways:
    
    - **Absolute Pressure** = the pressure relative to a vacuum (think of this as the total pressure taking everything into account)
    - **Gauge Pressure** = the pressure relative to the atmosphere (the pressure not taking atmospheric pressure into account)
    - Absolute Pressure = Gauge Pressure + Atmospheric Pressure
        - Atmospheric Pressure is the same thing as air pressure
            - Unless otherwise stated, air pressure (pressure exerted on an object by just air) is considered to be 100,000 Pascals (However, you do NOT need to memorize this as it will be on your reference sheet during the exam)
- Expanding “absolute pressure = gauge pressure + atmospheric pressure” gives you an equation to find the pressure at any point in the fluid
    
- P = P(0) + ρgh
    
- P represents Absolute Pressure
    
- P(0) represents Atmospheric Pressure
    
- ρgh represents Gauge Pressure
    
    - h represents the vertical distance from the surface of the fluid to a point in the fluid we’re measuring for

$$ \large{P=P_i+\rho gh} $$

- Remember that the shape of the container the static fluid is in has no effect on the pressure calculated
    - As long as the distance between the surface of the fluid and the point we’re measuring for are the same, the container shape does not matter (assuming we’re using the same fluid with the same atmospheric pressure)
- **Pascal’s Law**: Any pressure exerted on one point/surface of a fluid causes an equal increase in pressure at all points throughout that fluid

## Applications of Static Fluids

- A U-shaped tube
    
    ![https://knowt-user-attachments.s3.amazonaws.com/afcb2543eed34a2cb2ffa637c1d884e1.jpeg](https://knowt-user-attachments.s3.amazonaws.com/afcb2543eed34a2cb2ffa637c1d884e1.jpeg)
    
    - If you have a U-shaped tube container with fluid inside, the surface of the fluid on both sides should be at the same height because they have the same absolute and atmospheric pressure
    - The bottom line: Force exerted on the bottom of the U-tube must be equal for both sides of the tube
- Hydraulic Jack
    
    ![https://knowt-user-attachments.s3.amazonaws.com/2e99188766454084b2c406d51fc2eadb.jpeg](https://knowt-user-attachments.s3.amazonaws.com/2e99188766454084b2c406d51fc2eadb.jpeg)
    
    - Typically, on the AP exam, you’ll see pistons with different areas
    - The same principle applies: the force exerted on the bottom of the container is the same for each side

Therefore, F1(A1) = F2(A2)

1. **Barometer**: a device used to measure the pressure acting on the surface of a fluid
    - A tube filled with fluid is turned upside down (with the opening facing into the container) into a container with that same fluid
        - The leftover air is pulled up in the test tube, creating a vacuum in the top of the tube
            - Remember, this is a vacuum so no forces are exerted, pulling up on the mercury.
    - The pressure at the point at the water level of the main container will be equal to the pressure of the column of fluid in the test tube

## Buoyancy

- Because we know that gauge pressure in a static fluid increases with depth, the pressure from water pushing up on the block is greater than the pressure pushing down on the top of the block
    
    - Remember that pressure acting on the sides of the block will cancel out
- This difference in pressure must be accounted for otherwise no block would be able to float in water
    
    - This is the **force of buoyancy** - the upward force on an object equal to the weight of the fluid that was displaced by the body
- Force of buoyancy = the weight of displaced fluid = mg = (ρV)g
    
    $$ \large{F=(\rho V)g} $$
    

## Dynamic Fluids

- Dynamic fluids - fluids that are moving (fluid flowing through a pipe)
- **Volume Flow Rate** - the volume of the fluid that flows past a certain point every second (units are m^3/s)
- Volume Flow Rate = Av
    - A = cross-sectional area of the pipe
    - v = velocity of the fluid
- If the pipe is full (which we typically assume it is in AP Physics 2), the volume flow rate must be constant throughout the pipe
    - This means if the pipe widens, the velocity decreases, and vice versa
    - This is called the continuity principle
        - This is why if you put a thumb over a hose, the water sprays out with more velocity
- **Bernoulli’s Equation** - An equation typically used to solve situations when a fluid is flowing from point to point
    - This equation is a statement of conservation of energy
- P + ρgh + 1/2 ρv^2 is constant
    - As you can see, this equation looks very similar to equations of kinetic energy (1/2 mv^2) and gravitational potential energy (mgh) used in Physics 1
    - Here’s the bottom line: where the flow of a fluid is faster, the pressure is lower

## Applications of Dynamic Fluids

- Airplanes and wings
    
    ![https://knowt-user-attachments.s3.amazonaws.com/c79b3e9afe9d4da7aeaf0e4e161227c1.jpeg](https://knowt-user-attachments.s3.amazonaws.com/c79b3e9afe9d4da7aeaf0e4e161227c1.jpeg)
    
    - The air above the wing is compressed, creating a greater velocity of the air above the wing and therefore, a difference in pressure between above and below the wing
        - This effect is called lift
- Curveball
    
    ![https://knowt-user-attachments.s3.amazonaws.com/e65d08f4d4834fd280fc32796f39b6a5.jpeg](https://knowt-user-attachments.s3.amazonaws.com/e65d08f4d4834fd280fc32796f39b6a5.jpeg)
    
    - Friction between a ball and the air makes air drag past faster on one side of the ball, creating a pressure difference that curves the trajectory