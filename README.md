# AT_JS_HT3
**Testing Dropbox API with Postman PLUS Jenkins file**

This project was created in order to provide functional test automation of 3 scenarios (below) for [Dropbox API](https://www.dropbox.com/developers/documentation/http/documentation).

### HT Sources
Here you can find sources which are requested in the task

* GitHub repo: ooops, actually you're already here 🙃
* Jenkins completed job folder is here too as 'jenkins_build' 😉
* [Postman collection link](https://www.getpostman.com/collections/1090c70eaed21acf3b54). **Note!** There's no secret credentionals, they're assigned as env variables.

## Scenarios

* #1 scenario - Upload a file:
**precondition: script must authorize in the site with the credentials specified in the collection variables, the path to the file is defined (i.e. in collection variables).**

Scenario:

1. Upload the file (max size - 150MB) with POST request to `https://content.dropboxapi.com/2/files/upload`
2. Check the response status is 200 and the path from the request and the response are the same
3. Save a file hash in the collection variables from the response

*Comments: details of this API request are [here](https://www.dropbox.com/developers/documentation/http/documentation#files-upload)

* #2 scenario - Get metadata of a file:
**precondition: script must authorize in the site with the credentials specified in the collection variables, file hash of the uploaded file is saved (i.e. in collection variables), the path to the file is defined (i.e. in collection variables).**

Scenario:

1. GET request with path to the file to `https://api.dropboxapi.com/2/files/get_metadata`
2. Check the response status is 200 and file hash from the request and the response are the same

*Comments: details of this API request are [here](https://www.dropbox.com/developers/documentation/http/documentation#files-get_metadata)

* #3 scenario - Delete a file:
**precondition: script must authorize in the site with the credentials specified in the collection variables, the path to the file is saved (i.e. in collection variables).**

Scenario:

1. DELETE request to `https://api.dropboxapi.com/2/files/delete_v2` and path to the file in the body
2. Check the response status is 200

*Comments: details of this API request are [here](https://www.dropbox.com/developers/documentation/http/documentation#files-delete)

## Technologies used

- [Jenkins](https://www.jenkins.io/)
- [POSTMAN](https://www.postman.com/)
- [NEWMAN](https://www.npmjs.com/package/newman)
