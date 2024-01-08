## Running the Demo Agents

This document guides you through setting up and running the demo agents for Aries Cloud Agent Python.

**Prerequisites:**

* Docker installed and running locally
* Terminal access

**Steps:**

1. **Navigate to the demo directory:**

   ```
   cd aries-cloudagent-python/demo
   ```

2. **Start the demo agents:**

   - **Alice:**
      ```
      LEDGER_URL=http://dev.greenlight.bcovrin.vonx.io ./run_demo alice
      ```
      ![Screenshot](alice-agent-running-in-terminal.png)
   - **Faber:**
      ```
      LEDGER_URL=http://dev.greenlight.bcovrin.vonx.io ./run_demo faber
      ```
      ![Screenshot](faber-agent-running-in-terminal.png)
   - **Acme:**
      ```
      LEDGER_URL=http://dev.greenlight.bcovrin.vonx.io ./run_demo acme
      ```
      ![Screenshot](acme-running-in-terminal.png)

3. **Access Agent APIs:**

   - **Alice:** http://0.0.0.0:8031/api/doc#/
   ![Screenshot](alice-agent-api.png)
   - **Faber:** http://0.0.0.0:8021/api/doc#/
   ![Screenshot](faber-agent-api.png)
   - **Acme:** http://0.0.0.0:8041/api/doc#/
   ![Screenshot](acme-api-endpoints.png)

4. **Connect Alice and Faber:**

   - Copy the invitation details from Faber's API.
   - Paste the invitation details into Alice's API to create a connection.

5. **Test interactions:**

   The following activities are available for testing agent interactions:

   - **(1) Issue Credential:** Issue a credential from Faber to Alice.
   - **(2) Send Proof Request:** Faber requests a proof from Alice.
   - **(2a) Send *Connectionless* Proof Request:** Faber requests a proof from Alice without an established connection (requires a mobile client).
   - **(3) Send Message:** Send a message between agents.
   - **(4) Create New Invitation:** Create a new invitation in the specified agent.
   - **(T) Toggle tracing on credential/proof exchange:** Enable or disable tracing for debugging purposes.
   - **(X) Exit:** Close the demo agent.

**Additional Information:**

- The invitation details will look similar to this:

```json
{
  "@type": "https://didcomm.org/out-of-band/1.1/invitation",
  "@id": "d81f4d89-edeb-4412-b11a-d91fa9c10e6d",
  "label": "faber.agent",
  "handshake_protocols": ["https://didcomm.org/didexchange/1.0"],
  "services": [
    {
      "id": "#inline",
      "type": "did-communication",
      "recipientKeys": ["did:key:z6MkpvgF5rr28x2kHUBoJUbu5H38tiHcqihfCPad273EsZu5#z6MkpvgF5rr28x2kHUBoJUbu5H38tiHcqihfCPad273EsZu5"],
      "serviceEndpoint": "http://host.docker.internal:8020"
    }
  ]
}
```

**More Information at** 
```https://github.com/hyperledger/aries-cloudagent-python/tree/main/demo#readme```
