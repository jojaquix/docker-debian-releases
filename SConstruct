# Copyright (C) 2019 Leandro Lisboa Penz <lpenz@lpenz.org>
# This file is subject to the terms and conditions defined in
# file 'LICENSE', which is part of this source code package.

import os

pjoin = os.path.join

if False:
    Environment = None

env = Environment(ENV=os.environ)
env.Command("_apt-mirrors.json", ['apt-mirrors-info'], "./$SOURCE $TARGET")

for gobase in ['apt-mirrors-info']:
    env.Command(gobase,
                [pjoin('go/cmd', gobase, 'main.go'), 'go/common/common.go'],
                'go build ' + pjoin('./go/cmd', gobase))