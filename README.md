# go-zero-demo


goctl api plugin -plugin goctl-swagger="swagger -filename docs/swagger.json --host localhost:8888 --basepath /" --api desc/main.api --dir .


goctl api go --api desc/main.api --dir . --style go_zero  


## npx openapi-ts
{
  "devDependencies": {
    "@hey-api/openapi-ts": "^0.96.1"
  },
  "dependencies": {
    "@hey-api/client-axios": "^0.9.1",
    "axios": "^1.15.2"
  }
}

## openapi-ts.config.ts
import { defineConfig } from '@hey-api/openapi-ts';

export default defineConfig({
  input: './docs/swagger.json',
  output: './src/api/types',
  plugins: [
    '@hey-api/client-axios',  // 用 axios
    '@hey-api/sdk',           // 生成请求函数
  ],
});