ifeq ($(CONFIG_OF),y)

dtb-$(CONFIG_ARCH_TEGRA) += 	tegra124-mocha.dtb \

targets += dtbs
targets += $(dtb-y)
endif

# *.dtb used to be generated in the directory above. Clean out the
# old build results so people don't accidentally use them.
dtbs: $(addprefix $(obj)/, $(dtb-y))
	$(Q)rm -f $(obj)/../*.dtb

clean-files := *.dtb
