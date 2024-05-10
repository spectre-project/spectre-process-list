# Process List

Cross-platform native method to receive the list of the launched
processes.

## Cloning spectre-process-list

```
git clone https://github.com/spectre-project/spectre-process-list
cd spectre-process-list
npm install
```

## Supported OS

* `Windows` Windows 7+, Windows Server 2008 R2+
* `Linux` any Linux-based distributives
* `OS X` *Soon...*

## Usage
```js
const { snapshot } = require("process-list");

const tasks = await snapshot('pid', 'name');
console.log(tasks);

// output
// [{
//    name: "1.exe",
//    pid: 1234,
// }, ... ]
```

## API

##### `snapshot(...field: String): Promise<[]Object>`
Returns the list of the launched processes.

##### `allowedFields: []String`
List of allowed fields.

* `pid: Number` - process pid
* `ppid: Number` - parent process pid
* `name: String` - process name (title)
* `path: String` - full path to the process binary file
* `threads: Number` - threads per process
* `owner: String` - the owner of the process
* `priority: Number` - an os-specific process priority
* `cmdline: String` - full command line of the process
* `starttime: Date` - the process start date / time
* `vmem: String` - virtual memory size in bytes used by process
* `pmem: String` - physical memory size in bytes used by process
* `cpu: Number` - cpu usage by process in percent
* `utime: String` - amount of time in ms that this process has been scheduled in user mode
* `stime: String` - amount of time that in ms this process has been scheduled in kernel mode

## License

MIT, Copyright &copy; 2014 - 2019 Dmitry Tsvettsikh
