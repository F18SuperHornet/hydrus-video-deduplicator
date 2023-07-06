<div align="center">
  
 # Hydrus Video Deduplicator
  <img src="https://github.com/appleappleapplenanner/hydrus-video-deduplicator/assets/104981058/e65383e8-1978-46aa-88b6-6fdda9767367">
  
Hydrus Video Deduplicator detects similar video files and marks them as potential duplicates through the Hydrus API

</div>

---

## How It Works:
The deduplicator works by comparing videos by computing a perceptual hash.

A perceptual hash is a way to characterize videos in small chunks.

The perceptual hashes are stored in a database file in the running directory to avoid computing them every time.

Once all perceptual hashes for all the videos in your database are computed, they are compared against each other to detect if they're similar. If they are similar, they will be marked as potential duplicates in Hydrus.

The accuracy is extremely good because of [vpdq](https://github.com/facebook/ThreatExchange/tree/main/vpdq). You can adjust the threshold of similarity using `--threshold`. The default is 75%.

For more information check out the [wiki](https://github.com/appleappleapplenanner/hydrus-video-deduplicator/wiki) and the [FAQ](https://github.com/appleappleapplenanner/hydrus-video-deduplicator/wiki/faq)

---

## Installation:
#### Dependencies:
- Python >=3.10
- FFmpeg

```sh
python3 -m pip install hydrusvideodeduplicator
```

---

## [Usage:](https://github.com/appleappleapplenanner/hydrus-video-deduplicator/wiki/Usage)

```sh
python3 -m hydrusvideodeduplicator --api-key="<your key>"
```

---

## TODO:
- [ ] Option to rollback and remove potential duplicates
- [ ] OR predicates for --query
- [ ] Parallelize hashing and duplicate search
- [ ] Automatically generate access key with Hydrus API
- [x] Docker container
- [ ] Upload Docker container to Docker Hub (GitHub Action)
- [x] Pure Python port of vpdq
- [x] Windows compatibility without WSL or Docker

Please create an issue on Github if you have any problems or questions! Pull requests are also welcome.

---

## Credits:
[Hydrus Network](https://github.com/hydrusnetwork/hydrus) by dev

[Hydrus API Library](https://gitlab.com/cryzed/hydrus-api) by Cryzed

[pdq](https://github.com/facebook/ThreatExchange/tree/main/pdq) by Meta

vpdq by Meta, ported to Python by me.

[Big Buck Bunny](https://peach.blender.org/about) clips by Blender Foundation (CC BY 3.0)
