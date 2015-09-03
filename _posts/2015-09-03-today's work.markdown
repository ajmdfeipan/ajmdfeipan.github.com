---
layout: post
title:  "今天的工作!"
date:   2015-09-03 19:02:05
categories: work
---
1. github blog
  - github.io,  setting-> gen page 测一下
  - jekyll：
          - gem源:

                      gem sources --remove https://rubygems.org/
                      $ gem sources -a https://ruby.taobao.org/
                      $ gem sources -l
          - 新建 jekyll new xxoo
          - 内测 jekyll server
          - To github  git add/commit/push
          - edit publish
          - markdown
            - 代码 内嵌`注意输入法` ；块空行＋4*TAB

2. portel start
   - mysql
       - mac fail:
            - pycharm(pip):
                － 问题

                      dlopen(/Users/jp/v_falcon/lib/python2.7/site-packages/_mysql.so, 2): Library not loaded: libmysqlclient.18.dylib
                      Referenced from: /Users/jp/v_falcon/lib/python2.7/site-packages/_mysql.so Reason: image not found

                － 解决 `sudo ln -s /usr/local/mysql/lib/libmysqlclient.18.dylib /usr/lib/libmysqlclient.18.dylib`

      - redmine:
        - my.cnf: bind
        - sudo ufw allow 3306
        - local shell :`mysql -uroot -p -e "grant all privileges on *.* to 'bitnami'@'%' identified by '2566248c0a'"`

   - uic req:
      - kill uic part:

            @app.before_request
            def before_request():
            p = request.path
            for ignore_pre in IGNORE_PREFIX:
              if p.startswith(ignore_pre):
                  return

            if 'user_name' in session and session['user_name']:
                g.user_name = session['user_name']
            else:
                # sig = request.cookies.get('sig')
                # if not sig:
                #     return redirect_to_sso()
                #
                # username = uic.username_from_sso(sig)
                # if not username:
                #     return redirect_to_sso()
                #
                # session['user_name'] = username
                g.user_name = 'jj'#session['user_name']
3. go server
