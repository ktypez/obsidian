First install python on the pc you want to share the files from, [Python downloads](https://www.python.org/downloads/). Go to the directory where the folder/file you want to share folder/file resides. Now open the powershell in the respective drive or navigate to that directory. Now use the following command to spawn a http server. Use `shift+right click`, `open powershell here`. Or open a powershell, and use `cd [folder path]`.


```text
python -m http.server
```

or

```text
python3 -m http.server
```

Then a python server will already be running on the directory, you wrote the command from.

Now let’s find the local ip address assinged to the same pc where the server was spawned.