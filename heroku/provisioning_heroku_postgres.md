# データベースを作成する

## 確認

Use the `heroku addons` command to determine whether your app already has Heroku Postgres provisioned:
```
$ heroku addons
Owning App         Add-on                          Plan                Price  State  
─────────────────  ──────────────────────────────  ──────────────────  ─────  ───────
ayumu-astrowalker  cloudinary-perpendicular-23425  cloudinary:starter  free   created
dabyss             papertrail-contoured-83965      papertrail:choklad  free   created
```

## 作成

If `heroku-postgresql` doesn’t appear in your app’s list of add-ons, you can provision it with the following CLI command:

```
$ heroku addons:create heroku-postgresql:<PLAN_NAME>
```
For example:
```
$ heroku addons:create heroku-postgresql:mini -a ayumu-astrowalker
Creating heroku-postgresql:mini on ⬢ ayumu-astrowalker... $5/month
Database has been created and is available
 ! This database is empty. If upgrading, you can transfer
 ! data from another database with pg:copy
```

これでできた
```
$ heroku addons
Owning App         Add-on                          Plan                    Price     State  
─────────────────  ──────────────────────────────  ──────────────────────  ────────  ───────
ayumu-astrowalker  cloudinary-perpendicular-23425  cloudinary:starter      free      created
ayumu-astrowalker  postgresql-clean-66547          heroku-postgresql:mini  $5/month  created
dabyss             papertrail-contoured-83965      papertrail:choklad      free      created
```
