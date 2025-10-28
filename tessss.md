# 🔄 Vagrant Shared Folders: Host ↔ Guest

---

### 🧭 What are Host and Guest in Vagrant?

- **Host**: Your physical machine (e.g., Windows, macOS).
- **Guest**: The virtual machine (VM) that Vagrant spins up (usually Linux).

---

### 📁 What’s Happening with `/vagrant`?

When you run `vagrant up`, Vagrant automatically **syncs a folder** between your host and guest:

- On your **host**: the folder where your `Vagrantfile` lives.
- On your **guest VM**: it appears as `/vagrant`.

So any changes you make in:
- `~/myproject` on your laptop → show up in `/vagrant` inside the VM.
- `/vagrant` inside the VM → reflect back in your laptop folder.

---

### 💡 Why is this Useful?

- Edit code using your favorite editor on your laptop.
- Run and test that code inside the VM (e.g., Linux environment).
- No need to copy files back and forth — it's seamless!

---

### 🛠️ Customize Shared Folders (Optional)

You can define custom synced folders in your `Vagrantfile`:

```ruby
config.vm.synced_folder "src/", "/home/vagrant/app"
