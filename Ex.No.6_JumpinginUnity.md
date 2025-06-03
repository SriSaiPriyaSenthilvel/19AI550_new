# Ex.No: 6  Implementation of Jumping  behaviour- Unity
### DATE:                                                                            
### REGISTER NUMBER : 212222240103
### AIM: 
To write a program to simulate the process of jumping in Unity.
### Algorithm:

1. Create a new 3D Unity project
2. Add a Plane
3. Right-click Hierarchy → 3D Object → Plane → Rename to Ground
4. Add a Cube (Player)
5. Right-click Hierarchy → 3D Object → Cube → Rename to Player
6. Set Position: (0, 0.5, 0)
7. Add a Rigidbody to the Player
8. With the Player selected: Inspector → Add Component → Rigidbody
9. Set Constraints > Freeze Rotation X, Z (optional for stability)
10.Create the Jump Script and Apply the Script Player
11.Run the game
Press Play
Press Spacebar to jump
Your cube should only jump when touching the ground

###
**Program **
```
using UnityEngine;

public class PlayerJump : MonoBehaviour
{
    private Rigidbody rb;
    public float jumpForce = 5f;
    private bool isGrounded;

    void Start()
    {
        rb = GetComponent<Rigidbody>();
    }

    void Update()
    {
        if (Input.GetKeyDown(KeyCode.Space) && isGrounded)
        {
            rb.AddForce(Vector3.up * jumpForce, ForceMode.Impulse);
            isGrounded = false;
        }
    }

    private void OnCollisionEnter(Collision collision)
    {
        if (collision.gameObject.CompareTag("Ground"))
        {
            isGrounded = true;
        }
    }
}
```
### Output:

![image](https://github.com/user-attachments/assets/1815f016-1df9-4893-a324-6eaed021824e)

![image](https://github.com/user-attachments/assets/5b582539-d143-477c-a7a0-37203282b20d)

Jumping:

![image](https://github.com/user-attachments/assets/b86d05a3-8e0f-46bf-bf43-80e5a68d9357)

![image](https://github.com/user-attachments/assets/9e9ba1d0-ac08-4a13-bfc6-9777680fe443)

### Result:
Thus the simple jumping behavior was implemented successfully.
