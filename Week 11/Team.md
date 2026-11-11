Reese W: 
using UnityEngine;

public class HealthPack : MonoBehaviour
{
    private void OnTriggerEnter2D(Collider2D other)
    {
        PlayerHealth playerHealth = other.GetComponent<PlayerHealth>();

        if (playerHealth != null)
        {
            if (playerHealth.health < 100)
            {
                playerHealth.AddHealth(10);
            }

            Destroy(gameObject);
        }
    }
}
using UnityEngine;
using UnityEngine.InputSystem;

public class Playerattack : MonoBehaviour
{
    public Animator animator;

void Start()
    {

    }
    void Update()
    {
        Attack();
    }
    void Attack()
    {
        if (Keyboard.current.fKey.isPressed)
        {
            animator.SetBool("attack", true);
        }
        else
        {
            animator.SetBool("attack", false);
        }
    }
}
Klaudia L.:
using UnityEngine;

public class Trap : MonoBehaviour
{
    public PlayerHealth playerHealth;

    private void OnTriggerEnter2D(Collider2D other)
    {
        if (other.CompareTag("Player"))
        {
            playerHealth.health -= 10;
        }
    }
}