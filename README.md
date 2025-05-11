# Guesser code

package com.skyllx.guesser;

import java.util.Random;

public class Guesser {
	int guesserNumber;
	
	public int guessNumber() {
		System.out.println("Guesser,Please guess the number from 1-10");
		Random r = new Random();
		guesserNumber = r.nextInt(1,11);
		return guesserNumber;
	}

}

# Player Code
package com.skyllx.player;

import java.util.Scanner;

public class Player {
	int playerNumber;
	
	public int guessNumber() {
		System.out.println("Player, Player please guess the number from (1-10");
		Scanner scan = new Scanner(System.in);
		playerNumber = scan.nextInt();
		return playerNumber;
		
	}

}

# Umpire Code

package com.skyllx.umpire;

import com.skyllx.guesser.Guesser;
import com.skyllx.player.Player;

public class Umpire {
	int numberFromGuesser;
	int numberFromPlayer1;
	int numberFromPlayer2;
	int numberFromPlayer3;
	
	public void collectNumberFromGuesser() {
		Guesser g = new Guesser();
		numberFromGuesser = g.guessNumber();
	}
	
	public void collerctNumberFromPlayer() {
		Player p1 = new Player();
		numberFromPlayer1 = p1.guessNumber();
		
		Player p2 = new Player();
		numberFromPlayer1 = p2.guessNumber();
		
		
		Player p3 = new Player();
		numberFromPlayer1 = p3.guessNumber();
		
	}
	public void compare() {
		System.out.println("the Guesser Guess the number:"+ numberFromGuesser);
		if (numberFromGuesser == numberFromPlayer1) {
			System.out.println("Player1 wins");
		}
		if (numberFromGuesser == numberFromPlayer2) {
			System.out.println("Player2 wins");
		}
		if (numberFromGuesser == numberFromPlayer3) {
			System.out.println("Player3 wins");
		}
		if(numberFromGuesser != numberFromPlayer1 && numberFromGuesser != numberFromPlayer2 && numberFromGuesser != numberFromPlayer3) {
			System.out.println("Game Lost,Please Try Again!!!");
		}
		
	}
}

# Main 

package com.skyllx.main;

import com.skyllx.umpire.Umpire;

public class MainApp {
	public static void main(String[] args) {
		Umpire u = new Umpire();
		u.collectNumberFromGuesser();
		u.collerctNumberFromPlayer();
		u.compare();
	}

}

