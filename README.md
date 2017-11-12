usage

# Instantiate instance_tools class into ephemeral
ephemeral = ephemeral_disk.tools(force=1)

# Create new SWAP primary partition with 8GB if ephemeral disk was replaced, also create /opt partition and format it
ephemeral.create_disk_partition('/dev/xvdb', '8G', '1','c1.medium')

# Format new partition as SWAP and enable it afterwards
ephemeral.enable_swap('/dev/xvdb1')

# Format new partition created as EXT4
ephemeral.format_as_ext4('/dev/xvdb2')

# Mount as /opt the new partition
ephemeral.mount_partition('/dev/xvdb2', '/opt')

