# Phira Chart Standard

## Basic Chart Structure

A Phira chart package is a zip file. After extraction, the root of the zip should contain the following files directly (not in subfolders):

- `info.yml`: [Chart info](./chartinfo) file in YAML format
- Other files as specified in `info.yml`

## Supported Files

### Chart Files

See [Chart file formats](./chart-format/).

### Music Files

See [Music file format](./music).

TBD

## FAQ

RPE chart JSON files may store metadata (creator, difficulty, name, etc.). This is **not recommended**, as it can duplicate information and cause inconsistency. Phira uses `info.yml` as the source of truth.
