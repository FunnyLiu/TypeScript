# 源码分析


## 文件结构

``` bash
├── AUTHORS.md
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── CopyrightNotice.txt
├── Dockerfile
├── Gulpfile.js
├── LICENSE.txt
├── README.md
├── ThirdPartyNoticeText.txt
├── bin
|  ├── tsc
|  └── tsserver
├── lib - 由src文件中内容通过gulp生成而来
├── scripts - 各种构建用脚本
├── src
|  ├── cancellationToken
|  |  ├── cancellationToken.ts
|  |  └── tsconfig.json
|  ├── compiler
|  |  ├── binder.ts
|  |  ├── builder.ts
|  |  ├── builderPublic.ts
|  |  ├── builderState.ts
|  |  ├── builderStatePublic.ts
|  |  ├── checker.ts
|  |  ├── commandLineParser.ts
|  |  ├── core.ts
|  |  ├── corePublic.ts
|  |  ├── debug.ts
|  |  ├── diagnosticMessages.json
|  |  ├── emitter.ts
|  |  ├── factory.ts
|  |  ├── factoryPublic.ts
|  |  ├── moduleNameResolver.ts
|  |  ├── moduleSpecifiers.ts
|  |  ├── parser.ts
|  |  ├── path.ts
|  |  ├── perfLogger.ts
|  |  ├── performance.ts
|  |  ├── performanceTimestamp.ts
|  |  ├── program.ts
|  |  ├── resolutionCache.ts
|  |  ├── scanner.ts
|  |  ├── semver.ts
|  |  ├── sourcemap.ts
|  |  ├── symbolWalker.ts
|  |  ├── sys.ts
|  |  ├── transformer.ts
|  |  ├── transformers
|  |  |  ├── classFields.ts
|  |  |  ├── declarations
|  |  |  |  └── diagnostics.ts
|  |  |  ├── declarations.ts
|  |  |  ├── destructuring.ts
|  |  |  ├── es2015.ts
|  |  |  ├── es2016.ts
|  |  |  ├── es2017.ts
|  |  |  ├── es2018.ts
|  |  |  ├── es2019.ts
|  |  |  ├── es5.ts
|  |  |  ├── esnext.ts
|  |  |  ├── generators.ts
|  |  |  ├── jsx.ts
|  |  |  ├── module
|  |  |  |  ├── es2015.ts
|  |  |  |  ├── module.ts
|  |  |  |  └── system.ts
|  |  |  ├── ts.ts
|  |  |  └── utilities.ts
|  |  ├── tsbuild.ts
|  |  ├── tsbuildPublic.ts
|  |  ├── tsconfig.json
|  |  ├── tsconfig.release.json
|  |  ├── types.ts
|  |  ├── utilities.ts
|  |  ├── utilitiesPublic.ts
|  |  ├── visitor.ts
|  |  ├── visitorPublic.ts
|  |  ├── watch.ts
|  |  ├── watchPublic.ts
|  |  └── watchUtilities.ts
|  ├── debug
|  |  ├── debug.ts
|  |  └── tsconfig.json
|  ├── harness
|  |  ├── client.ts
|  |  ├── collections.ts
|  |  ├── compiler.ts
|  |  ├── documents.ts
|  |  ├── evaluator.ts
|  |  ├── fakes.ts
|  |  ├── fourslash.ts
|  |  ├── fourslashInterface.ts
|  |  ├── harness.ts
|  |  ├── harnessGlobals.ts
|  |  ├── harnessLanguageService.ts
|  |  ├── harnessUtils.ts
|  |  ├── loggedIO.ts
|  |  ├── runnerbase.ts
|  |  ├── sourceMapRecorder.ts
|  |  ├── tsconfig.json
|  |  ├── typeWriter.ts
|  |  ├── utils.ts
|  |  ├── vfs.ts
|  |  ├── virtualFileSystemWithWatch.ts
|  |  └── vpath.ts
|  ├── instrumenter
|  |  ├── instrumenter.ts
|  |  └── tsconfig.json
|  ├── jsTyping
|  |  ├── jsTyping.ts
|  |  ├── shared.ts
|  |  ├── tsconfig.json
|  |  └── types.ts
|  ├── lib
|  |  ├── README.md
|  |  ├── dom.generated.d.ts
|  |  ├── dom.iterable.d.ts
|  |  ├── dom.iterable.generated.d.ts
|  |  ├── es2015.collection.d.ts
|  |  ├── es2015.core.d.ts
|  |  ├── es2015.d.ts
|  |  ├── es2015.full.d.ts
|  |  ├── es2015.generator.d.ts
|  |  ├── es2015.iterable.d.ts
|  |  ├── es2015.promise.d.ts
|  |  ├── es2015.proxy.d.ts
|  |  ├── es2015.reflect.d.ts
|  |  ├── es2015.symbol.d.ts
|  |  ├── es2015.symbol.wellknown.d.ts
|  |  ├── es2016.array.include.d.ts
|  |  ├── es2016.d.ts
|  |  ├── es2016.full.d.ts
|  |  ├── es2017.d.ts
|  |  ├── es2017.full.d.ts
|  |  ├── es2017.intl.d.ts
|  |  ├── es2017.object.d.ts
|  |  ├── es2017.sharedmemory.d.ts
|  |  ├── es2017.string.d.ts
|  |  ├── es2017.typedarrays.d.ts
|  |  ├── es2018.asyncgenerator.d.ts
|  |  ├── es2018.asynciterable.d.ts
|  |  ├── es2018.d.ts
|  |  ├── es2018.full.d.ts
|  |  ├── es2018.intl.d.ts
|  |  ├── es2018.promise.d.ts
|  |  ├── es2018.regexp.d.ts
|  |  ├── es2019.array.d.ts
|  |  ├── es2019.d.ts
|  |  ├── es2019.full.d.ts
|  |  ├── es2019.object.d.ts
|  |  ├── es2019.string.d.ts
|  |  ├── es2019.symbol.d.ts
|  |  ├── es2020.d.ts
|  |  ├── es2020.full.d.ts
|  |  ├── es2020.string.d.ts
|  |  ├── es2020.symbol.wellknown.d.ts
|  |  ├── es5.d.ts - es5的声明文件，js规范的基本声明
|  |  ├── es5.full.d.ts
|  |  ├── esnext.bigint.d.ts
|  |  ├── esnext.d.ts
|  |  ├── esnext.full.d.ts
|  |  ├── esnext.intl.d.ts
|  |  ├── header.d.ts
|  |  ├── libs.json
|  |  ├── scripthost.d.ts
|  |  ├── webworker.generated.d.ts
|  |  └── webworker.importscripts.d.ts
|  ├── server
|  |  ├── editorServices.ts
|  |  ├── packageJsonCache.ts
|  |  ├── project.ts
|  |  ├── protocol.ts
|  |  ├── scriptInfo.ts
|  |  ├── scriptVersionCache.ts
|  |  ├── session.ts
|  |  ├── tsconfig.json
|  |  ├── types.ts
|  |  ├── typesMap.json
|  |  ├── typingsCache.ts
|  |  ├── utilities.ts
|  |  ├── utilitiesPublic.ts
|  |  └── watchType.ts
|  ├── services
|  |  ├── breakpoints.ts
|  |  ├── classifier.ts
|  |  ├── codeFixProvider.ts
|  |  ├── codefixes
|  |  |  ├── addConvertToUnknownForNonOverlappingTypes.ts
|  |  |  ├── addMissingAwait.ts
|  |  |  ├── addMissingConst.ts
|  |  |  ├── addMissingDeclareProperty.ts
|  |  |  ├── addMissingInvocationForDecorator.ts
|  |  |  ├── addNameToNamelessParameter.ts
|  |  |  ├── annotateWithTypeFromJSDoc.ts
|  |  |  ├── convertConstToLet.ts
|  |  |  ├── convertFunctionToEs6Class.ts
|  |  |  ├── convertToAsyncFunction.ts
|  |  |  ├── convertToEs6Module.ts
|  |  |  ├── convertToMappedObjectType.ts
|  |  |  ├── correctQualifiedNameToIndexedAccessType.ts
|  |  |  ├── disableJsDiagnostics.ts
|  |  |  ├── fixAddMissingMember.ts
|  |  |  ├── fixAddMissingNewOperator.ts
|  |  |  ├── fixAddModuleReferTypeMissingTypeof.ts
|  |  |  ├── fixAwaitInSyncFunction.ts
|  |  |  ├── fixCannotFindModule.ts
|  |  |  ├── fixClassDoesntImplementInheritedAbstractMember.ts
|  |  |  ├── fixClassIncorrectlyImplementsInterface.ts
|  |  |  ├── fixClassSuperMustPrecedeThisAccess.ts
|  |  |  ├── fixConstructorForDerivedNeedSuperCall.ts
|  |  |  ├── fixEnableExperimentalDecorators.ts
|  |  |  ├── fixEnableJsxFlag.ts
|  |  |  ├── fixExtendsInterfaceBecomesImplements.ts
|  |  |  ├── fixForgottenThisPropertyAccess.ts
|  |  |  ├── fixInvalidImportSyntax.ts
|  |  |  ├── fixJSDocTypes.ts
|  |  |  ├── fixSpelling.ts
|  |  |  ├── fixStrictClassInitialization.ts
|  |  |  ├── fixUnreachableCode.ts
|  |  |  ├── fixUnusedIdentifier.ts
|  |  |  ├── fixUnusedLabel.ts
|  |  |  ├── helpers.ts
|  |  |  ├── importFixes.ts
|  |  |  ├── inferFromUsage.ts
|  |  |  ├── removeUnnecessaryAwait.ts
|  |  |  ├── requireInTs.ts
|  |  |  ├── useBigintLiteral.ts
|  |  |  └── useDefaultImport.ts
|  |  ├── completions.ts
|  |  ├── documentHighlights.ts
|  |  ├── documentRegistry.ts
|  |  ├── exportAsModule.ts
|  |  ├── findAllReferences.ts
|  |  ├── formatting
|  |  |  ├── README.md
|  |  |  ├── formatting.ts
|  |  |  ├── formattingContext.ts
|  |  |  ├── formattingScanner.ts
|  |  |  ├── rule.ts
|  |  |  ├── rules.ts
|  |  |  ├── rulesMap.ts
|  |  |  └── smartIndenter.ts
|  |  ├── getEditsForFileRename.ts
|  |  ├── globalThisShim.ts
|  |  ├── goToDefinition.ts
|  |  ├── importTracker.ts
|  |  ├── jsDoc.ts
|  |  ├── navigateTo.ts
|  |  ├── navigationBar.ts
|  |  ├── organizeImports.ts
|  |  ├── outliningElementsCollector.ts
|  |  ├── patternMatcher.ts
|  |  ├── preProcess.ts
|  |  ├── refactorProvider.ts
|  |  ├── refactors
|  |  |  ├── addOrRemoveBracesToArrowFunction.ts
|  |  |  ├── convertExport.ts
|  |  |  ├── convertImport.ts
|  |  |  ├── convertParamsToDestructuredObject.ts
|  |  |  ├── extractSymbol.ts
|  |  |  ├── extractType.ts
|  |  |  ├── generateGetAccessorAndSetAccessor.ts
|  |  |  └── moveToNewFile.ts
|  |  ├── rename.ts
|  |  ├── services.ts
|  |  ├── shims.ts
|  |  ├── signatureHelp.ts
|  |  ├── smartSelection.ts
|  |  ├── sourcemaps.ts
|  |  ├── stringCompletions.ts
|  |  ├── suggestionDiagnostics.ts
|  |  ├── symbolDisplay.ts
|  |  ├── textChanges.ts
|  |  ├── transform.ts
|  |  ├── transpile.ts
|  |  ├── tsconfig.json
|  |  ├── types.ts
|  |  └── utilities.ts
|  ├── shims
|  |  ├── mapShim.ts
|  |  └── tsconfig.json
|  ├── testRunner
|  |  ├── compilerRunner.ts
|  |  ├── externalCompileRunner.ts
|  |  ├── fourslashRunner.ts
|  |  ├── parallel
|  |  |  ├── host.ts
|  |  |  ├── shared.ts
|  |  |  └── worker.ts
|  |  ├── projectsRunner.ts
|  |  ├── runner.ts
|  |  ├── rwcRunner.ts
|  |  ├── test262Runner.ts
|  |  ├── tsconfig.json
|  |  └── unittests
|  |     ├── asserts.ts
|  |     ├── base64.ts
|  |     ├── builder.ts
|  |     ├── comments.ts
|  |     ├── compilerCore.ts
|  |     ├── config
|  |     |  ├── commandLineParsing.ts
|  |     |  ├── configurationExtension.ts
|  |     |  ├── convertCompilerOptionsFromJson.ts
|  |     |  ├── convertTypeAcquisitionFromJson.ts
|  |     |  ├── initializeTSConfig.ts
|  |     |  ├── matchFiles.ts
|  |     |  ├── projectReferences.ts
|  |     |  ├── showConfig.ts
|  |     |  └── tsconfigParsing.ts
|  |     ├── convertToBase64.ts
|  |     ├── createMapShim.ts
|  |     ├── customTransforms.ts
|  |     ├── evaluation
|  |     |  ├── asyncArrow.ts
|  |     |  ├── asyncGenerator.ts
|  |     |  ├── awaiter.ts
|  |     |  ├── forAwaitOf.ts
|  |     |  ├── forOf.ts
|  |     |  ├── objectRest.ts
|  |     |  └── optionalCall.ts
|  |     ├── factory.ts
|  |     ├── incrementalParser.ts
|  |     ├── jsDocParsing.ts
|  |     ├── moduleResolution.ts
|  |     ├── parsePseudoBigInt.ts
|  |     ├── paths.ts
|  |     ├── printer.ts
|  |     ├── programApi.ts
|  |     ├── publicApi.ts
|  |     ├── reuseProgramStructure.ts
|  |     ├── semver.ts
|  |     ├── services
|  |     |  ├── cancellableLanguageServiceOperations.ts
|  |     |  ├── colorization.ts
|  |     |  ├── convertToAsyncFunction.ts
|  |     |  ├── documentRegistry.ts
|  |     |  ├── extract
|  |     |  |  ├── constants.ts
|  |     |  |  ├── functions.ts
|  |     |  |  ├── helpers.ts
|  |     |  |  ├── ranges.ts
|  |     |  |  └── symbolWalker.ts
|  |     |  ├── hostNewLineSupport.ts
|  |     |  ├── languageService.ts
|  |     |  ├── organizeImports.ts
|  |     |  ├── patternMatcher.ts
|  |     |  ├── preProcessFile.ts
|  |     |  ├── textChanges.ts
|  |     |  └── transpile.ts
|  |     ├── transform.ts
|  |     ├── tsbuild
|  |     |  ├── amdModulesWithOut.ts
|  |     |  ├── containerOnlyReferenced.ts
|  |     |  ├── demo.ts
|  |     |  ├── emitDeclarationOnly.ts
|  |     |  ├── emptyFiles.ts
|  |     |  ├── exitCodeOnBogusFile.ts
|  |     |  ├── graphOrdering.ts
|  |     |  ├── helpers.ts
|  |     |  ├── inferredTypeFromTransitiveModule.ts
|  |     |  ├── javascriptProjectEmit.ts
|  |     |  ├── lateBoundSymbol.ts
|  |     |  ├── missingExtendedFile.ts
|  |     |  ├── moduleSpecifiers.ts
|  |     |  ├── outFile.ts
|  |     |  ├── referencesWithRootDirInParent.ts
|  |     |  ├── resolveJsonModule.ts
|  |     |  ├── sample.ts
|  |     |  ├── transitiveReferences.ts
|  |     |  ├── watchEnvironment.ts
|  |     |  └── watchMode.ts
|  |     ├── tsc
|  |     |  ├── declarationEmit.ts
|  |     |  ├── helpers.ts
|  |     |  ├── incremental.ts
|  |     |  └── listFilesOnly.ts
|  |     ├── tscWatch
|  |     |  ├── consoleClearing.ts
|  |     |  ├── emit.ts
|  |     |  ├── emitAndErrorUpdates.ts
|  |     |  ├── helpers.ts
|  |     |  ├── incremental.ts
|  |     |  ├── programUpdates.ts
|  |     |  ├── resolutionCache.ts
|  |     |  ├── watchApi.ts
|  |     |  └── watchEnvironment.ts
|  |     └── tsserver
|  |        ├── applyChangesToOpenFiles.ts
|  |        ├── cachingFileSystemInformation.ts
|  |        ├── cancellationToken.ts
|  |        ├── compileOnSave.ts
|  |        ├── completions.ts
|  |        ├── configFileSearch.ts
|  |        ├── configuredProjects.ts
|  |        ├── declarationFileMaps.ts
|  |        ├── documentRegistry.ts
|  |        ├── duplicatePackages.ts
|  |        ├── events
|  |        |  ├── largeFileReferenced.ts
|  |        |  ├── projectLanguageServiceState.ts
|  |        |  ├── projectLoading.ts
|  |        |  └── projectUpdatedInBackground.ts
|  |        ├── externalProjects.ts
|  |        ├── forceConsistentCasingInFileNames.ts
|  |        ├── formatSettings.ts
|  |        ├── getApplicableRefactors.ts
|  |        ├── getEditsForFileRename.ts
|  |        ├── getExportReferences.ts
|  |        ├── helpers.ts
|  |        ├── importHelpers.ts
|  |        ├── importSuggestionsCache.ts
|  |        ├── inferredProjects.ts
|  |        ├── languageService.ts
|  |        ├── maxNodeModuleJsDepth.ts
|  |        ├── metadataInResponse.ts
|  |        ├── navTo.ts
|  |        ├── occurences.ts
|  |        ├── openFile.ts
|  |        ├── packageJsonInfo.ts
|  |        ├── projectErrors.ts
|  |        ├── projectReferenceCompileOnSave.ts
|  |        ├── projectReferenceErrors.ts
|  |        ├── projectReferences.ts
|  |        ├── projects.ts
|  |        ├── refactors.ts
|  |        ├── reload.ts
|  |        ├── rename.ts
|  |        ├── resolutionCache.ts
|  |        ├── session.ts
|  |        ├── skipLibCheck.ts
|  |        ├── smartSelection.ts
|  |        ├── symLinks.ts
|  |        ├── syntaxOperations.ts
|  |        ├── telemetry.ts
|  |        ├── textStorage.ts
|  |        ├── typeAquisition.ts
|  |        ├── typeReferenceDirectives.ts
|  |        ├── typingsInstaller.ts
|  |        ├── untitledFiles.ts
|  |        ├── versionCache.ts
|  |        └── watchEnvironment.ts
|  ├── tsc
|  |  ├── executeCommandLine.ts
|  |  ├── tsc.ts
|  |  ├── tsconfig.json
|  |  └── tsconfig.release.json
|  ├── tsconfig-base.json
|  ├── tsconfig-library-base.json
|  ├── tsconfig-noncomposite-base.json
|  ├── tsconfig.json
|  ├── tsserver
|  |  ├── server.ts
|  |  └── tsconfig.json
|  ├── tsserverlibrary
|  |  ├── tsconfig.json
|  |  └── tsserverlibrary.ts
|  ├── typescriptServices
|  |  ├── tsconfig.json
|  |  └── typescriptServices.ts
|  ├── typingsInstaller
|  |  ├── nodeTypingsInstaller.ts
|  |  └── tsconfig.json
|  ├── typingsInstallerCore
|  |  ├── tsconfig.json
|  |  └── typingsInstaller.ts
|  └── watchGuard
|     ├── tsconfig.json
|     └── watchGuard.ts

directory: 2685 file: 53084

ignored: directory (17)

```



# TypeScript

[![Build Status](https://travis-ci.org/microsoft/TypeScript.svg?branch=master)](https://travis-ci.org/microsoft/TypeScript)
[![VSTS Build Status](https://dev.azure.com/typescript/TypeScript/_apis/build/status/Typescript/node10)](https://dev.azure.com/typescript/TypeScript/_build/latest?definitionId=4&view=logs)
[![npm version](https://badge.fury.io/js/typescript.svg)](https://www.npmjs.com/package/typescript)
[![Downloads](https://img.shields.io/npm/dm/typescript.svg)](https://www.npmjs.com/package/typescript)

[TypeScript](https://www.typescriptlang.org/) is a language for application-scale JavaScript. TypeScript adds optional types to JavaScript that support tools for large-scale JavaScript applications for any browser, for any host, on any OS. TypeScript compiles to readable, standards-based JavaScript. Try it out at the [playground](https://www.typescriptlang.org/play/), and stay up to date via [our blog](https://blogs.msdn.microsoft.com/typescript) and [Twitter account](https://twitter.com/typescript).

Find others who are using TypeScript at [our community page](https://www.typescriptlang.org/community/).

## Installing

For the latest stable version:

```bash
npm install -g typescript
```

For our nightly builds:

```bash
npm install -g typescript@next
```

## Contribute

There are many ways to [contribute](https://github.com/microsoft/TypeScript/blob/master/CONTRIBUTING.md) to TypeScript.
* [Submit bugs](https://github.com/microsoft/TypeScript/issues) and help us verify fixes as they are checked in.
* Review the [source code changes](https://github.com/microsoft/TypeScript/pulls).
* Engage with other TypeScript users and developers on [StackOverflow](https://stackoverflow.com/questions/tagged/typescript).
* Help each other in the [TypeScript Community Discord](https://discord.gg/typescript).
* Join the [#typescript](https://twitter.com/search?q=%23TypeScript) discussion on Twitter.
* [Contribute bug fixes](https://github.com/microsoft/TypeScript/blob/master/CONTRIBUTING.md).
* Read the language specification ([docx](https://github.com/microsoft/TypeScript/blob/master/doc/TypeScript%20Language%20Specification.docx?raw=true),
 [pdf](https://github.com/microsoft/TypeScript/blob/master/doc/TypeScript%20Language%20Specification.pdf?raw=true), [md](https://github.com/microsoft/TypeScript/blob/master/doc/spec.md)).

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see
the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com)
with any additional questions or comments.

## Documentation

*  [TypeScript in 5 minutes](https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes.html)
*  [Programming handbook](https://www.typescriptlang.org/docs/handbook/basic-types.html)
*  [Language specification](https://github.com/microsoft/TypeScript/blob/master/doc/spec.md)
*  [Homepage](https://www.typescriptlang.org/)

## Building

In order to build the TypeScript compiler, ensure that you have [Git](https://git-scm.com/downloads) and [Node.js](https://nodejs.org/) installed.

Clone a copy of the repo:

```bash
git clone https://github.com/microsoft/TypeScript.git
```

Change to the TypeScript directory:

```bash
cd TypeScript
```

Install [Gulp](https://gulpjs.com/) tools and dev dependencies:

```bash
npm install -g gulp
npm install
```

Use one of the following to build and test:

```
gulp local             # Build the compiler into built/local.
gulp clean             # Delete the built compiler.
gulp LKG               # Replace the last known good with the built one.
                       # Bootstrapping step to be executed when the built compiler reaches a stable state.
gulp tests             # Build the test infrastructure using the built compiler.
gulp runtests          # Run tests using the built compiler and test infrastructure.
                       # Some low-value tests are skipped when not on a CI machine - you can use the
                       # --skipPercent=0 command to override this behavior and run all tests locally.
                       # You can override the specific suite runner used or specify a test for this command.
                       # Use --tests=<testPath> for a specific test and/or --runner=<runnerName> for a specific suite.
                       # Valid runners include conformance, compiler, fourslash, project, user, and docker
                       # The user and docker runners are extended test suite runners - the user runner
                       # works on disk in the tests/cases/user directory, while the docker runner works in containers.
                       # You'll need to have the docker executable in your system path for the docker runner to work.
gulp runtests-parallel # Like runtests, but split across multiple threads. Uses a number of threads equal to the system
                       # core count by default. Use --workers=<number> to adjust this.
gulp baseline-accept   # This replaces the baseline test results with the results obtained from gulp runtests.
gulp lint              # Runs eslint on the TypeScript source.
gulp help              # List the above commands.
```


## Usage

```bash
node built/local/tsc.js hello.ts
```


## Roadmap

For details on our planned features and future direction please refer to our [roadmap](https://github.com/microsoft/TypeScript/wiki/Roadmap).
