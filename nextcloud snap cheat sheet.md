## Nextcloud.occ Command List (Snap Installation)

1. **Status and Maintenance:**
   - `nextcloud.occ status` - Check the status of your Nextcloud instance.
   - `nextcloud.occ maintenance:mode --on` - Enable maintenance mode.
   - `nextcloud.occ maintenance:mode --off` - Disable maintenance mode.

2. **User Management:**
   - `nextcloud.occ user:add <username> [--password <password>]` - Create a new user.
   - `nextcloud.occ user:delete <username>` - Delete a user.
   - `nextcloud.occ user:enable <username>` - Enable a disabled user.
   - `nextcloud.occ user:disable <username>` - Disable a user.
   - `nextcloud.occ user:resetpassword <username>` - Reset a user's password.

3. **App Management:**
   - `nextcloud.occ app:list` - List installed apps.
   - `nextcloud.occ app:enable <app_name>` - Enable an app.
   - `nextcloud.occ app:disable <app_name>` - Disable an app.

4. **Database Operations:**
   - `nextcloud.occ db:convert-type` - Convert the database to a different type.
   - `nextcloud.occ db:add-missing-indices` - Add missing indices to the database tables.
   - `nextcloud.occ db:add-missing-columns` - Add missing columns to the database tables.
   - `nextcloud.occ db:convert-filecache-bigint` - Convert the `filecache` table to use bigint IDs.

5. **Maintenance and Repair:**
   - `nextcloud.occ maintenance:repair` - Perform various maintenance and repair operations.
   - `nextcloud.occ maintenance:mode --on` - Enable maintenance mode.
   - `nextcloud.occ maintenance:mode --off` - Disable maintenance mode.

6. **Other Commands:**
   - `nextcloud.occ config:list` - List the current configuration values.
   - `nextcloud.occ config:system:set <parameter> <value>` - Set a system configuration parameter.
   - `nextcloud.occ config:system:get <parameter>` - Get the value of a system configuration parameter.

## Nextcloud.occ Command System Configuration Parameters

1. **Set System Configuration Parameters:**
   - `nextcloud.occ config:system:set <parameter> <value>` - Set a system configuration parameter.

   Example usages:
   - Set the maximum upload size:
     ```shell
     nextcloud.occ config:system:set upload_max_size --value=512M
     ```

   - Set the default language:
     ```shell
     nextcloud.occ config:system:set default_language --value="en_US"
     ```

2. **Get System Configuration Parameters:**
   - `nextcloud.occ config:system:get <parameter>` - Get the value of a system configuration parameter.

   Example usages:
   - Get the Nextcloud version:
     ```shell
     nextcloud.occ config:system:get version
     ```

   - Get the trusted domains:
     ```shell
     nextcloud.occ config:system:get trusted_domains
     ```

3. **List All System Configuration Parameters:**
   - `nextcloud.occ config:list` - List all the current configuration values.

   Example usage:
   ```shell
   nextcloud.occ config:list

## Parameters for `nextcloud.occ config:system:get` Command

- `version`: Retrieves the Nextcloud version.
- `instanceid`: Retrieves the unique instance ID of your Nextcloud installation.
- `trusted_domains`: Retrieves the list of trusted domains configured for your Nextcloud instance.
- `datadirectory`: Retrieves the path to the data directory where Nextcloud stores user data.
- `default_language`: Retrieves the default language set for Nextcloud.
- `default_locale`: Retrieves the default locale used for Nextcloud.
- `overwrite.cli.url`: Retrieves the URL used for Nextcloud command-line interface (CLI) operations.
- `mail_smtpmode`: Retrieves the configured SMTP mode for sending emails from Nextcloud.
- `maintenance`: Retrieves the status of maintenance mode (enabled or disabled).
- `filelocking.enabled`: Retrieves the status of file locking (enabled or disabled).
- `memcache.locking`: Retrieves the configured memory cache used for file locking.
- `ldapIgnoreNamingRules`: Retrieves the LDAP ignore naming rules setting.
- `logtimezone`: Retrieves the configured timezone for logging.
- `logfile`: Retrieves the path to the log file used by Nextcloud.

These are just a few examples of parameters that can be used with the `nextcloud.occ config:system:get` command. You can explore other system configuration parameters by referencing the Nextcloud documentation or using the `nextcloud.occ config:list` command to list all available configuration parameters.

## Parameters that can be set with `nextcloud.occ config:system:set`

- `overwrite.cli.url`: Sets the URL used for Nextcloud command-line interface (CLI) operations.
- `mail_smtpmode`: Sets the configured SMTP mode for sending emails from Nextcloud.
- `maintenance`: Sets the status of maintenance mode (enable or disable).
- `filelocking.enabled`: Sets the status of file locking (enable or disable).
- `memcache.locking`: Sets the configured memory cache used for file locking.
- `ldapIgnoreNamingRules`: Sets the LDAP ignore naming rules setting.
- `logtimezone`: Sets the configured timezone for logging.
- `trusted_domains`: Sets the list of trusted domains configured for your Nextcloud instance.
- `loglevel`: Sets the log level for Nextcloud logging.
- `updater.release.channel`: Sets the release channel for Nextcloud updates.
- `default_language`: Sets the default language for Nextcloud.
- `default_locale`: Sets the default locale for Nextcloud.
- `skeletondirectory`: Sets the path to the skeleton directory for new users.
- `knowledgebaseenabled`: Enables or disables the Nextcloud knowledge base app.
- `integrity.excluded.files`: Sets a list of files to be excluded from Nextcloud integrity checks.
- `integrity.check.disabled`: Disables Nextcloud integrity checks.
- `theme`: Sets the active theme for Nextcloud.
- `trashbin_retention_obligation`: Sets the retention period for items in the Nextcloud trash bin.

These parameters can be modified using the `nextcloud.occ config:system:set` command, allowing you to adjust the corresponding settings as needed.

Please note that modifying system configuration parameters should be done with caution, as improper changes may impact the functionality and security of your Nextcloud instance. It is recommended to refer to the official Nextcloud documentation and follow best practices when modifying these parameters.


## Msql DB Management

- sudo nextcloud.occ config:system:set dbpassword --value="<new_password>"

- sudo nextcloud.occ config:system:get dbuser

- sudo nextcloud.occ config:system:set dbuser --value="<new_username>"

## The Config File location

The `config.php` file for Nextcloud is typically located in the Nextcloud installation directory. The exact path may vary depending on your system and installation method.

If you have installed Nextcloud using the Snap package, the default location of the `config.php` file is:

```
/var/snap/nextcloud/current/nextcloud/config/config.php
```

If you have installed Nextcloud using other methods, such as manual installation or package managers like apt or yum, the `config.php` file is commonly found in the Nextcloud installation directory, which can vary based on your configuration. It is often located in the `config` subdirectory.

For example, if you installed Nextcloud in the `/var/www/html/nextcloud` directory, the path to the `config.php` file would be:

```
/var/www/html/nextcloud/config/config.php
```

If you are unsure about the specific location of the `config.php` file in your installation, you can try searching for it using a command like:

```
sudo find / -name config.php
```

This command will search the entire filesystem for the `config.php` file and display its path once found. Note that this search might take some time, especially if you have a large filesystem.

Once you locate the `config.php` file, you can open it with a text editor to view its contents, including the database configuration details.


## Here is a simple markdown cheat sheet for Snap commands related to Nextcloud:

```markdown
# Nextcloud Snap Commands Cheat Sheet

## Refreshing a Snap

Update the Snap package to the latest version:

```bash
sudo snap refresh nextcloud
```

## Removing and Installing a Snap

To remove a Snap package:

```bash
sudo snap remove nextcloud
```

To install a Snap package:

```bash
sudo snap install nextcloud
```

## Refreshing the Core Snap

If you're experiencing issues with the Snap system itself, try refreshing the core Snap:

```bash
sudo snap refresh core
```

## Viewing System Logs

To view the system logs related to a specific Snap package:

```bash
journalctl -u snap.nextcloud.service
```

## Creating a Snapshot

To create a snapshot of the Nextcloud Snap:

```bash
sudo snap save nextcloud
```

## Listing Snapshots

To list all saved snapshots:

```bash
sudo snap saved
```

## Restoring a Snapshot

To restore a snapshot of the Nextcloud Snap:

```bash
sudo snap restore <snapshot-id>
```

Replace `<snapshot-id>` with the ID of the snapshot you want to restore.

## Exporting a Snapshot

To download the snapshot to a file:

```bash
sudo snap export-snapshot <snapshot-id> <filename>
```

Replace `<snapshot-id>` with the ID of the snapshot you want to export and `<filename>` with the name of the file you want to save the snapshot to.

Remember that these snapshots are saved in `/var/lib/snapd/snapshots/` directory. If you're planning to backup these snapshots, consider backing up this directory.
```
