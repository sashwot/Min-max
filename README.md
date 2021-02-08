# Min-max
C# min/max game
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Number : MonoBehaviour
{
    int max = 1000;
    int min = 1;
    int guess = 500;
    // Start is called before the first frame update
    void Start()
    {
        StartGame();
        
    }

    void StartGame()
    {
         max = 1000;
         min = 1;
         guess = 500;
        Debug.Log("Welcome to number wizard");
        Debug.Log("Pick a number: ");
        Debug.Log("Highest number: " + max);
        Debug.Log("Lowest number: " + min);
        Debug.Log("Tell me if your guess is higher or lower then: " + guess);
        Debug.Log("Pushup = Higher, pushdown = lower, pushEnter=Correct");
        max = max + 1;
    }

    // Update is called once per frame
    void Update()
    {
        if (Input.GetKeyDown(KeyCode.UpArrow))
        {
            min = guess;
            NextGuess();
            
            
        }

        else if(Input.GetKeyDown(KeyCode.DownArrow))
        {
            max = guess;
            NextGuess();
        }

        else if(Input.GetKeyDown(KeyCode.Return))
        {
            Debug.Log("Correct....");
            StartGame();
        }
    }
    void NextGuess()
    {
        guess = (min + max) / 2;
        Debug.Log("Is it higher or lower then...." + guess);
    }
}

