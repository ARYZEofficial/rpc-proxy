### Example of usage

```JS
const apiUrl='https://raw.githubusercontent.com/ARYZEofficial/rpc-proxy/main/rpcUrls.json';

fetch(apiUrl, {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    // Add any other required headers here
  },
  body: JSON.stringify(requestData) // Convert the object to JSON
})
  .then(response => {
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
   const res = response.json(); // Parse the JSON response

    // rpcUrlsForMainnet = res["0x1"].rpcUrls
    return res;
  })
  .then(data => {
    // Handle the API response data here
    console.log(data);
  })
  .catch(error => {
    // Handle errors here
    console.error('There was a problem with the fetch operation:', error);
  });




```
