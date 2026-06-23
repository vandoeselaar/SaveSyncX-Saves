# SaveSyncX-Saves

Community save game collection for use with [SaveSyncX](https://github.com/vandoeselaar/SaveSyncX) — an original Xbox homebrew tool for backing up and restoring save games.

---

## Structure

```
/
├── list.json                          # Save index (used by SaveSyncX)
└── savegames/
    └── <title_id>/
        └── <savename>.zip             # Save game archive
```

Each game has its own folder named after its Xbox title ID (e.g. `4541005b` for Burnout 3). Save files are stored as `.zip` archives containing the raw UDATA ~~or TDATA~~ save structure.

---

## Contributing

Want to add a save? Great — contributions are welcome via Pull Request.

### Requirements

- The save must be from an original Xbox game (not Xbox 360)
- The `.zip` must contain a valid save structure as found on the Xbox hard drive (`UDATA/<title_id>/` or `TDATA/<title_id>/`)
- One save per PR is preferred to keep reviews manageable

### Steps

1. Fork this repository
2. Add your save zip to `savegames/<title_id>/`
3. Update `list.json` with the new entry (see format below)
4. Open a Pull Request with a short description of the save

### list.json format

```json
{
  "title_id": "4541005b",
  "game_name": "Burnout 3: Takedown",
  "saves": [
    {
      "id": "unique_save_id",
      "label": "Short description shown in SaveSyncX",
      "file": "savegames/4541005b/filename.zip",
      "size_bytes": 17550,
      "author": "YourUsername",
      "notes": "Any extra info (completion %, unlocks, etc.)"
    }
  ]
}
```

- `id` must be unique across the entire `list.json`
- `size_bytes` is the size of the `.zip` file
- `author` is your username or handle — or `Unknown` if the origin is unclear

### Finding the title ID

The title ID is the 8-character hex folder name under `UDATA\` or `TDATA\` on your Xbox hard drive. You can also look it up on sites like [dbox](https://dbox.tools/) or in community databases.

---

## Notes

- All saves in this repository are shared by the community for preservation and convenience
- Do not submit saves that contain personal information or account credentials
- Saves from pirated or illegitimately obtained games are not welcome
- This repository is not affiliated with Microsoft
