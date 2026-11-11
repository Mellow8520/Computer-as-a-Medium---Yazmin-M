###
using TMPro;
using UnityEngine;
using UnityEngine.InputSystem;

public class PlayerMana : MonoBehaviour
{
    public int mana = 100;

    public TMP_Text manaText;

    public Animator animator;

    void Start()
    {
        UpdateManaText();
    }

    void Update()
    {
        if (Keyboard.current != null &&
            Keyboard.current.eKey.wasPressedThisFrame)
        {
            if (mana >= 10)
            {
                mana -= 10;

                UpdateManaText();

                animator.SetTrigger("mam");
            }
        }
    }

    void UpdateManaText()
    {
        if (manaText != null)
        {
            manaText.text = "Mana: " + mana;
        }
    }
}
