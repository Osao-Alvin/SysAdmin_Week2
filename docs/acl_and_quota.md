# ACL and Quota Configuration

## 1. ACL Configuration

### 1.1 Public Folder (`/projects/public`)

# Give admin group read-execute permissions on /projects/public
sudo setfacl -m g:admin:rx /projects/public

# Give editor group read-execute permissions on /projects/public
sudo setfacl -m g:editor:rx /projects/public

# Give viewer group read-execute permissions on /projects/public
sudo setfacl -m g:viewer:rx /projects/public



### 1.2 Team Folder ('/projects/team')
# Grant editor group full access (read-write-execute) on /projects/team
sudo setfacl -m g:editor:rwx /projects/team

# Grant viewer group read-only access (read-execute) on /projects/team
sudo setfacl -m g:viewer:rx /projects/team

# Remove all access for others (no access) on /projects/team
sudo setfacl -m o::--- /projects/team



### 1.3 Confidential Folder ('/projects/confidential')
# Grant admin group full access (read-write-execute) on /projects/confidential
sudo setfacl -m g:admin:rwx /projects/confidential

# Remove all access for others (no access) on /projects/confidential
sudo setfacl -m o::--- /projects/confidential
