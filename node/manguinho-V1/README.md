# Boilerplate - Manguinho V1
By: [Rodrigo Manguinho]('https://www.linkedin.com/in/rmanguinho')

## Dependencies
- ✅ [git-commit-msg-linter](#git-commit-msg-linter)
- ✅ [Typescript](#typescript)
- ✅ [ESlint with Typescript](#eslint)
- ✅ [Husky](#husky)
- ✅ [lint-staged](#lint-staged)
- ✅ [Jest](#jest)

## Description

### git-commit-msg-linter 

Block commits that don't follow the pattern from [Conventional Commits]('https://www.conventionalcommits.org/en/v1.0.0/#summary').

> git commit -m "chore: add package"

([link]('https://github.com/legend80s/git-commit-msg-linter'))

### Typescript

Add typing for JavaScript.

```
# tsconfig.json

{
  "compilerOptions": {
    "outDir": "./dist",
    "module": "commonjs",
    "target": "ES2022",
    "esModuleInterop": true,
    "allowJs": true,
    "strictNullChecks": true
  }
}
```

- After compile will save files into "dist" folder
- target: defines the ECMAScript rules

([link]('https://www.typescriptlang.org/'))

### ESlint with Typescript

Analyzes your code and find JavaScript code problems.

```
# .eslintrc.json

{
  "extends": "standard-with-typescript",
  "parserOptions": {
    "project": "./tsconfig.json"
  }
}
```

This assures that it will read the ".tsconfig.json" file to run.

([link]('https://github.com/standard/eslint-config-standard-with-typescript'))

### Husky

Create hooks to execute when certain thing happens. Here we are using to execute [Lint-staged](#lint-staged) in pre-commits.

([link]('https://github.com/typicode/husky'))

### Lint-staged 

Run linters on staged git files preventing the commit of not working code.

```
# .lintstagedrc.json

{
  "*.ts": [
    "eslint 'src/**' --fix", 
    "npm run test:staged", 
    "git add"
    ]
}
```

- Applies for all .ts files
- Run only in the src folder
- Execute "test:staged" script
- Execute "git add"

([link]('https://github.com/okonet/lint-staged')) 

### Jest 

```
# jest.config.ts

// Indicates whether the coverage information should be collected while executing the test
collectCoverage: true,

// An array of glob patterns indicating a set of files for which coverage information should be collected
collectCoverageFrom: ['<rootDir>/src/**/*.ts'],

// The directory where Jest should output its coverage files
coverageDirectory: 'coverage',

// Indicates which provider should be used to instrument code for coverage
coverageProvider: 'v8',

// A list of paths to directories that Jest should use to search for files in
roots: [
    '<rootDir>/src'
],

// A map from regular expressions to paths to transformers
transform: {
    '.+\\.ts$': 'ts-jest'
}
```

([link]('https://github.com/facebook/jest'))