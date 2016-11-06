# HaloCustomsLobby
Keiner hat dich gefragt.
# Was habe ich getan?
    private String getRemoteUrl() throws Exception {
    AWSElasticBeanstalkGitPushRequest request = new AWSElasticBeanstalkGitPushRequest();
    request.setHost(getGitPushHost());

    Region region = RegionUtils.getRegionByEndpoint(environment.getRegionEndpoint());
    request.setRegion(region.getId());
    request.setApplication(environment.getApplicationName());

    if (!skipEnvironmentDeployment) {
        request.setEnvironment(environment.getEnvironmentName());
    }
    AWSGitPushAuth auth = new AWSGitPushAuth(request);
    URI uri = auth.deriveRemote(accessKey, secretKey);

    return uri.toString();
    }
no
