
### Log submission

For B1+B2/B3/B4 challenges, proof of runtime via logs is required.

There is fairly verbose logging enabled by default for the node software in Testnets, so we've created a small tool `retrieve_minified_logs` to sample your full set of log files and output a summary that is acceptable for submission.

- [Download retrieve_minified_logs for Linux](https://client-distribution-testnet.concordium.com/retrieve_minified_logs-linux-v1)
- [Download retrieve_minified_logs for OS X](https://client-distribution-testnet.concordium.com/retrieve_minified_logs-macos-v1)
- [Download retrieve_minified_logs for Windows](https://client-distribution-testnet.concordium.com/retrieve_minified_logs-windows-v1.exe)


Simply run the relevant binary on your system where the Concordium Node has been running. The tool will output two files in the folder it is run.

**⚠️ These files must be submitted without modifications. Tampering with the summary log will be detected and result in disqualification from all challenges.**



### Log sizes & rotation

After running the node for a significant time you may find that you are running out of disk space on your node.

You can find your log file location by running:

```
docker inspect --format='{{.LogPath}}' <container_name_or_id>
```

Where the `<container_name_or_id>` is found by running `docker ps -a`.


**⚠️ Make sure you generate log summaries for submission _before_ clearing any logs!**


You can then clear out your current logs via the command line:

```
# On OSX / Linux
truncate -s 0 <log_path>

# On Windows
echo.> <log_path>
```

Repeat this process if the log size gets too large again.

Make sure to submit all your log summaries if you're doing any of the `B*` challenges.
