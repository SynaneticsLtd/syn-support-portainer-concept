# syn-support-watch-tower-concept

Initial idea: Deploy the Watchtower image locally to appliances to monitor for image upgrades and automatically update them. The ideal long-term solution would involve running them from Cloud Run, enabling full CI/CD implementation and allowing for notification and heartbeat integration.

Opened for further contributions and ideas.

- **GitHub - [containrrr/watchtower](https://github.com/containrrr/watchtower)**: A process for automating Docker container base image updates.
- **GitHub - [yorkshire-and-humber-care-record/fhir-appliance](https://github.com/yorkshire-and-humber-care-record/fhir-appliance)**: Documentation and configuration files for running Interweave Connect (aka FHIR Appliance).

---

## Ideas/Contributions

1. ~~**Container Running Off a Reverse Proxy?~~
   - Current container runs locally and does not require modification at the networking level.

2. **Testing Plan**
   - Set the image to an older version and shorten the watch period to validate automatic updates - set enviroment with short image update interval
   - ~~Validate the 3-month cycle (per documentation) for automated updates.~~ Was found that this is possible

3. **Select Environment for Testing**
   - Sandpit environments or local setups - Customer candidate for testing?

4. **Review Existing Environments**
   - Assess how customized they are.
   - Investigate how `docker-compose` can be altered to include Watchtower.
   - Preliminary findings suggest minimal interference from Watchtower in functionality - although it does appear to set its own network?

5. **Configuration Monitoring Solutions**
   - Explore GitHub workflows for configuration changes?
   - Investigate writing workflows using GitHub Docs.
   - CI/CD could be valuable for monitoring and managing configurations.
   - Explore methods to detect and manage configuration changes effectively?

6. **Authentication Concerns**
   - Evaluate potential disruptions due to authentication changes - see git hub workflows?
   - Identify how notifications can alert if issues arise - possible elastic solution?

7. **Heartbeat Implementation**
   - Consider implementing a heartbeat mechanism for Elastic Stack/if migrated to GCP heartbeat would be better?

8. **Cloud Migration**
   - Investigate migrating to Cloud Run.
   - Cloud Run could enhance CI/CD practicality and make alert handling more efficient.



--

## Testing Environment

- **Environment Setup**:
  - Running Docker Engine (Linux version required for engine compatibility) - Images Present
  
- **Container Status**:
  - Fully functional based on the `docker-compose.yml` file below.
