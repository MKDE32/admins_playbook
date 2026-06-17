# switch to root
| Command       | User becomes | Password used     | Login shell | Loads root env | HOME becomes `/root` | Changes directory | Keeps user env |
|--------------|-------------|------------------|-------------|----------------|----------------------|-------------------|----------------|
| `sudo -i`    | root        | your password     | ✅ yes      | ✅ yes         | ✅ yes               | ✅ yes (`/root`)  | ❌ no          |
| `sudo -s`    | root        | your password     | ❌ no       | ❌ mostly      | ❌ no                | ❌ no             | ✅ yes         |
| `sudo su`    | root        | your password     | ❌ no       | ❌ mostly      | ❌ no                | ❌ no             | ✅ yes         |
| `sudo su -`  | root        | your password     | ✅ yes      | ✅ yes         | ✅ yes               | ✅ yes (`/root`)  | ❌ no          |
| `su`         | root        | root password     | ❌ no       | ❌ mostly      | ❌ no                | ❌ no             | ✅ yes         |
| `su -`       | root        | root password     | ✅ yes      | ✅ yes         | ✅ yes               | ✅ yes (`/root`)  | ❌ no          |










































