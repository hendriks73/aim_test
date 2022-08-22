# aim_test

Demonstrates a GitHub Actions environment build failure for [AimStack](https://aimstack.io) and `pip 20.2.4` and earlier (i.e. before the "new resolver"):

```bash
Installing pip dependencies: ...working... ::warning::Pip subprocess error:
WARNING: Missing build requirements in pyproject.toml for aim==3.11.1 from https://files.pythonhosted.org/packages/a6/98/9aeccb650aec68978f7cf2f04f324233180fbb7d8746fbd2bd328dfc53b0/aim-3.11.1.tar.gz#sha256=176923340a609210a842d3c4761c51d83f51b2e3799329445cc803eff09b067a (from -r /home/runner/work/aim_test/aim_test/condaenv.wm7ml876.requirements.txt (line 1)).
WARNING: The project does not specify a build backend, and pip cannot fall back to setuptools without 'wheel'.
```

And:

```bash
Error compiling Cython file:
------------------------------------------------------------
...
        self.container.commit(batch)

    def keys_eager(
            self,
            path: Union[AimObjectKey, AimObjectPath] = (),
    ) -> List[Union[AimObjectPath, AimObjectKey]]:
             ^
------------------------------------------------------------
aim/storage/containertreeview.py:110:13: Compiler crash in AnalyseDeclarationsTransform
```

For more detailed failure info, fork and run the GH action.