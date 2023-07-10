# data

## fixed (images)

- an image is based on read-only data
- you can't change data inside an image unless you rebuild the image
- the application usually has code and environment code provided by the developer

## temporary (containers)

- fetched or produced inside the running container
- stored in memory or temporary files
- dinamyc and changing, but it is ok if it gets lost
- for instance: information in a form

## permanent app data (containers and volumes)

- database saved (persisted info)
- the data should survive the removal of a container
