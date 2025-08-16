# Docker Shared Volume Demo

## Purpose
This project demonstrates how multiple Docker containers can share the same volume for persistent storage.

## Steps
1. Create a volume
   ```bash
   docker volume create sharedvol
   ```

2. Run writer container and add a file
   ```bash
   docker run -it --name writer -v sharedvol:/data ubuntu bash
   echo "Hello from writer" > /data/note.txt
   ```

3. Run reader container and verify the file
   ```bash
   docker run -it --name reader -v sharedvol:/data ubuntu bash
   cat /data/note.txt
   ```

## Result
Both containers are able to access the same file stored in the volume.

---
This project is part of my Docker learning journey 🚀
