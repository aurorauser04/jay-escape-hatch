# jay-escape-hatch

End-to-end sample for externally built Microsoft Copilot Managed Runtime apps.
The app in `apps/escape-hatch` was created with `ms app create --repo none`.

The deployment workflow installs the public CLI, builds and packs the Vite app,
and deploys the external artifact using a dedicated service principal. It runs
on pushes to `main` that change the app or workflow, and supports manual runs.
The deployed page displays **Jay Escape Hatch** and an interactive counter.

Required repository secrets: `PP_SP_CLIENT_ID`, `PP_SP_CLIENT_SECRET`, and
`PP_SP_TENANT_ID`. Credentials are never stored in source control.

See the [deployment guide](https://learn.microsoft.com/en-us/microsoft-365/managed-apps/developer/deploy-managed-apps-github-actions)
for setup and prerequisites. Successful runs publish the app URL and CLI version
in their GitHub Actions summary.