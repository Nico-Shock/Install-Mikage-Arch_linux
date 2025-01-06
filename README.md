## **How to Install Mikage 3DS Emulator on Arch Linux**

1. **Install Requirements:**
   ```bash
   yay -S conan ninja cmake
   ```

2. **Install Mikage:**
   ```bash
   git clone https://github.com/mikage-emu/mikage-dev.git
   cd mikage-dev
   mkdir build
   cd build
   conan install .. -of . --build=missing
   cmake .. -G Ninja --toolchain conan_toolchain.cmake -DCMAKE_BUILD_TYPE=Release
   ninja && sudo ninja install
   ```

3. **Run a game:**
   ```bash
   cd build && source conanrun.sh && ./source/mikage game.cci --bootstrap_nand --launch_menu
   ```

### **MAKE SURE TO HAVE AN AES-KEY.TXT DUMP FROM YOUR 3DS THE SAME AS A BOOTSTRAP VIRTUAL NAND FROM YOUR GAME UPDATE PARTITION (ESHOP, HSHOP, GAMECARDS WORK THE SAME WITH FLASHCARDS)**
