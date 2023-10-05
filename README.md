### Example of usage

```JS

export default function useNetworks() {
  const [_networks, setNetworks] = useState<INetwork[]>([]);

  useEffect(() => {
    (async () => {
      const API_NETWORKS_URL = 'https://raw.githubusercontent.com/ARYZEofficial/rpc-proxy/main/rpcUrls.json';

      const response = await fetch(API_NETWORKS_URL);
      const res = (await response.json()).networks[0]; // Parse the JSON response

      const networkList = Object.keys(res).map((e) => res[e]) as INetwork[];
      setNetworks(networkList);
    })();
  }, [setNetworks]);

  const networks = useMemo(() => {
    return _networks.length > 0 ? _networks : [];
  }, [_networks]);

  return { networks };
}


```
