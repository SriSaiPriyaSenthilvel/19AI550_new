# Ex.No: 4  Implementation of Kinematic movement -seek behavior in Unity
### DATE:                                                                            
### REGISTER NUMBER : 212222240103
### AIM: 
To write a program to simulate the process of seek behavior in Unity without NavigationMeshAgent. 
### Algorithm:
1. Create a New Unity Project by Open the  Unity Hub and create a new 3D Project,Name the project (e.g., SeekBehaviorDemo).
2. Create the Moving Object
   In the Hierarchy, right-click → 3D Object → Cube (or Sphere).
   Rename it to Seeker and Reset its position:Select the Seeker, go to Inspector → Transform → Set Position to (0,0,0).
3. Create the Target Object
   Right-click in the Hierarchy → 3D Object → Sphere (or any other shape).
   Rename it to Target. Move it away from Seeker, e.g., set Position to (5, 0, 5).
   Select the Target, add a Material, and change the color. (if needed) 
4. Adding the Seek Behavior Script
   Create the Script-In the Project Window, go to the Assets folder.
   Right-click → Create → C# Script.
5. Write a script for seek behavior and save it
6. Attach the Script
   Select Seeker in the Hierarchy - Drag & Drop the SeekBehavior script onto the Inspector Panel.
   Drag & Drop the Target from the Hierarchy into the "Target" field in the script component.
12. Run the game 
13. Stop the program
    
### Program:
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Script : MonoBehaviour
{
    // Start is called before the first frame update
    public Transform target;  // The object to seek
    public float speed = 5f;  // Movement speed
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        if (target == null) return;  // Exit if no target is assigned

        // Calculate the desired direction
        Vector3 direction = (target.position - transform.position).normalized;

        // Move the object towards the target
        transform.position += direction * speed * Time.deltaTime;
    }
}
```
### Output:

Before:

![image](https://github.com/user-attachments/assets/84614456-dec4-4e7e-a0a3-36d05605dae6)

![image](https://github.com/user-attachments/assets/bdd7c971-e86f-4766-a53a-318f355e70a0)

After:

![image](https://github.com/user-attachments/assets/da12bfd0-c69b-405e-816d-06ac3aba0076)

![image](https://github.com/user-attachments/assets/042f80bd-b852-470c-8c19-83f550737f54)

### Result:
Thus the simple seek behavior was implemented successfully.
