# 2-step build

```
// 1 meteor.dockerfile -> wanglian/meteor-launchpad
docker build -f base.dockerfile -t wanglian/meteor-base .
// 2 weaworking.dockerfile -> wanglian/weaworking-launchpad
docker build \
  --build-arg INSTALL_PHANTOMJS=true \
  --build-arg INSTALL_GRAPHICSMAGICK=true \
  --build-arg NODE_VERSION=8.9.3 \
  --build-arg METEOR_VERSION=1.6.0.1 \
  -f meteor.dockerfile \
  -t wanglian/meteor-launchpad .
// then use wanglian/meteor-launchpad to build meteor app docker image
```