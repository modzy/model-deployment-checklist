# ML Model Deployment Checklist
An efficient, to-the-point, and easy-to-use checklist to following when deploying an ML model into production. Consider including a copy of this checklist alongside each model you plan to deploy to production.

MODEL NAME:___________________________________ </br>
MODEL ID:_____________________________________ </br>
MODEL VERSION:________________________________

### 💻 AFTER MODEL TRAINING
- [ ] Model assets are stored in communal location (e.g. weights files, processing code, list of dependencies)
- [ ] Model particulars are stored in communal location (e.g. training data, features used, input/output formats)
- [ ] Model creator's name and contact information is logged with model assets
- [ ] Model monitoring is in place
- [ ] Model assets are assembled into final production format (e.g. container, zip file, script)
  #### For new model versions
- [ ] New model version conforms to same input/output contract as previous model version ***-or-*** other production systems have been changed to accept a new contract

### 🧪 DURING DEPLOYMENT TO `TEST` ENVIRONMENT
- [ ] Model is uploaded or otherwise pushed to `test` environment
- [ ] Model version in test environment matches model version from training
- [ ] Model successfully runs on same infrastructure that will be used in production (e.g. same CPU, GPU, RAM settings)
- [ ] Model validation metrics in test environment match validation metrics that were run at the end of training
- [ ] Model response times are within an acceptable range when tested with representative sample of production data

### 🏛️ DURING DEPLOYMENT TO `PROD` ENVIRONMENT
- [ ] Model is uploaded or otherwise pushed to production environment
- [ ] Model version in production matches model version in test
- [ ] Access to the model is secured and requires authentication
- [ ] Other production systems can communicate with the model
- [ ] Model returns results
  #### For new model versions
- [ ] Production traffic is rerouted to new model version
- [ ] Old model version is shutdown

### 🔬 WHILE MODEL IS DEPLOYED TO `PROD` ENVIRONMENT
- [ ] Monitoring is in place to estimate and track model accuracy (aka model drift)
- [ ] Monitoring is in place to track model speed, latency, and throughput
- [ ] Monitoring is in place to track and log model errors including downtime
- [ ] Monitoring is in place to detect cybersecurity attacks

