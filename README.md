# rust-hot-reload-example

---

## Note: depends on cargo-watch crate to be installed

```sh
cargo install cargo-watch
```

* open two terminals each with their own command to run

	- the terminal that is building the main binary
		```sh
			cargo watch -i lib -x "run --features reload"
		```
	    - will watch for changes to the main.rs file. 

	- the terminal that is building the library module for hot reloading
	functions.
		```sh
			cargo watch -w lib -x 'build -p lib'
		```

	- make a change to the anything in the library file
	and the second terminal will rebuild the library.
	- and the first terminal will hot reload the library without
	interrupting the running executable and dynamically load the new library.

	- however, if anything was changed in the main file running in that terminal process
	this will rebuild the entire project again.
