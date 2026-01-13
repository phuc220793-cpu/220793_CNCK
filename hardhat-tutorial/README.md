# Dự án mẫu Hardhat 3 Beta (`mocha` và `ethers`)

Dự án này giới thiệu một dự án Hardhat 3 Beta sử dụng `mocha` để kiểm thử và thư viện `ethers` để tương tác với Ethereum.

Để tìm hiểu thêm về Hardhat 3 Beta, vui lòng truy cập [hướng dẫn Bắt đầu](https://hardhat.org/docs/getting-started#getting-started-with-hardhat-3). Để chia sẻ phản hồi của bạn, hãy tham gia nhóm Telegram [Hardhat 3 Beta](https://hardhat.org/hardhat3-beta-telegram-group) hoặc [mở một vấn đề](https://github.com/NomicFoundation/hardhat/issues/new) trong trình theo dõi vấn đề GitHub của chúng tôi.

## Tổng quan dự án

Dự án ví dụ này bao gồm:

- Một tệp cấu hình Hardhat đơn giản.

- Các bài kiểm thử đơn vị Solidity tương thích với Foundry.

- Các bài kiểm thử tích hợp TypeScript sử dụng `mocha` và ethers.js
- Các ví dụ minh họa cách kết nối với các loại mạng khác nhau, bao gồm cả việc mô phỏng cục bộ mạng chính OP.
## Usage

### Running Tests

Chạy tất cả các bài kiểm tra trong dự án, thực hiện lệnh sau:

```shell
npx hardhat test
```

Bạn cũng có thể chọn lọc chạy các bài kiểm tra Solidity hoặc `mocha`:

```shell
npx hardhat test solidity
npx hardhat test mocha
```

### Thực hiện triển khai lên Sepolia

Dự án này bao gồm một mô-đun Ignition ví dụ để triển khai hợp đồng. Bạn có thể triển khai mô-đun này lên một chuỗi được mô phỏng cục bộ hoặc lên Sepolia.

Để chạy quá trình triển khai lên chuỗi cục bộ:
```shell
npx hardhat ignition deploy ignition/modules/Counter.ts
```

Để chạy triển khai lên Sepolia, bạn cần một tài khoản có đủ tiền để gửi giao dịch. Cấu hình Hardhat được cung cấp bao gồm một Biến cấu hình có tên là `SEPOLIA_PRIVATE_KEY`, bạn có thể sử dụng biến này để thiết lập khóa riêng của tài khoản bạn muốn sử dụng.

Bạn có thể thiết lập biến `SEPOLIA_PRIVATE_KEY` bằng cách sử dụng plugin `hardhat-keystore` hoặc bằng cách thiết lập nó như một biến môi trường.

Để thiết lập biến cấu hình `SEPOLIA_PRIVATE_KEY` bằng `hardhat-keystore`:
```shell
npx hardhat keystore set SEPOLIA_PRIVATE_KEY
```

After setting the variable, you can run the deployment with the Sepolia network:

```shell
npx hardhat ignition deploy --network sepolia ignition/modules/Counter.ts
```
