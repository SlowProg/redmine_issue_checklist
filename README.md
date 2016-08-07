# Redmine Issue Checklist Plugin

This plugin enables you to add checklists to Redmine issues.

The initial author of the plugin is [Kirill Bezrukov](http://www.redminecrm.com/projects/checklist/pages/1) and [Danil Tashkinov](https://github.com/nodecarter).

## Compatibility

This plugin version is compatible only with Redmine 2.0 and later.

## Installation

1. To install the plugin
    * Download the .ZIP archive, extract files and copy the plugin directory into #{REDMINE_ROOT}/plugins.

    Or

    * Change you current directory to your Redmine root directory:  

            cd {REDMINE_ROOT}

      Copy the plugin from GitHub using the following commands:

            git clone https://github.com/SlowProg/redmine_issue_checklist.git plugins/redmine_issue_checklist

2. Update the Gemfile.lock file by running the following commands:  

         rm Gemfile.lock  
         bundle install

3. This plugin requires a migration. Run the following command to upgrade your database (make a database backup before):  

        bundle exec rake redmine:plugins:migrate RAILS_ENV=production

4. Restart Redmine.

Now you should be able to see the plugin in **Administration > Plugins**.

## Usage

The Redmine Issue Checklist plugin enables you to add checklists to Redmine issues.

You can configure the plugin:

1. Track the checklist changes in the issue log.

2. Change the issue done ratio based on the checklist progress.

3. Change the issue status when done ratio is 100%.

4. Change the issue status when done ratio rollback down from 100%.

To do this, go to **Administration > Plugins**, click **Configure** and select the corresponding check boxes.  
![plugin settings](issue_checklist_1.PNG)

To add a checklist to an issue, enter the checklist item text into the the **Checklist** field in the issue description and click the **+** button.  
![checklist item](issue_checklist_2.PNG)

You can add as many checklist items as you need. To rearrange the checklist, drag and drop the items in the desired order. To delete an item, click the trash bin icon.  
![checklist item](issue_checklist_3.PNG)

To mark the completed checklist items, select the corresponding check boxes. The plugin will display the changes in the issue log and change the issue done ratio, if you have configured it accordingly.  
![progress](issue_checklist_4.PNG)

To manage checklist-related permissions, go to **Administration > Roles and permissions**, click the role name and select or clear the required check boxes.  
![permissions](issue_checklist_5.PNG)

## Testing

Run tests using the following command:

    rake redmine:plugins:test NAME=redmine_issue_checklist RAILS_ENV=test_sqlite3

## License

Redmine Checklist plugin is open source and released under the terms of the GNU General Public License v2 (GPL).
