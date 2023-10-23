# Foo-


dnf repoquery --qf "%{name}" --all --queryformat "%{name}" | xargs -I {} dnf repoquery --requires {} | sort -u > dependencies.txt
dnf repoquery --qf "%{name}" --all --queryformat "%{name}" | sort -u > all_packages.txt
comm -23 all_packages.txt dependencies.txt
