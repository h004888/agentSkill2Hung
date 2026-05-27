---
name: interviewing-for-srs
description: Use when interviewing stakeholders, eliciting BA requirements, or completing an SRS document with sections for product overview, actors, use cases, software features, screens, non-functional requirements, business rules, and application messages.
---

# Interviewing For SRS

## Overview
SRS completion is evidence gathering, not guessing. Ask enough to map each answer into Product Overview, Actors, Use Cases, Features, Screens, NFRs, Business Rules, Messages, and Appendix with clear traceability.

## Core Rule
Never invent missing requirements. Mark unknowns as `TBD`, assumption, or decision needed.

## Interview Flow
1. Confirm product goal, scope, out-of-scope, stakeholders, success criteria.
2. Identify actors, external systems, permissions, notifications.
3. Elicit top business processes as use cases: trigger, precondition, main flow, alternatives, exceptions, postcondition.
4. Derive features, screens, data, business rules, messages from each use case.
5. Ask NFRs with measurable numbers: performance, security, availability, backup, audit, compatibility, integration.
6. Close gaps using traceability: every actor has use cases; every use case has feature/screen/data/rules/messages/NFRs where relevant.

## Quick Reference
| SRS section | Must capture |
|---|---|
| Product Overview | problem, users, value, scope, context diagram, external entities, components |
| Actors | actor name, description, goal, permissions, login need, notifications |
| Use Cases | ID, group, actor, trigger, pre/post-condition, main flow, alternative/exception flows |
| Software Features | feature name, priority, screens, actions, inputs, outputs, validation, acceptance criteria |
| Screens | screen name, purpose, fields, buttons, states, role access, navigation |
| Data | entities, fields, required/unique rules, relationships, retention, import/export |
| Business Rules | formulas, workflow states, limits, approvals, allowed transitions, violations |
| Messages | success, validation, business error, permission error, system error, confirmation |
| External Interfaces | UI, hardware, software/API, communication, third-party systems |
| Quality Attributes | response time, concurrent users, uptime, RPO/RTO, audit, security, compatibility |

## Question Bank

### 1. Product Overview
- Hệ thống giải quyết vấn đề kinh doanh gì?
- Ai dùng hệ thống, dùng trong bối cảnh nào?
- Phiên bản đầu gồm những gì? Cái gì chắc chắn ngoài phạm vi?
- Thành công đo bằng chỉ số nào?
- Có hệ thống hiện tại cần thay thế hoặc tích hợp không?
- Context diagram cần có thực thể ngoài nào: người dùng, hệ thống, thiết bị, dịch vụ?

### 2. Actors
- Những nhóm người/hệ thống nào tương tác với hệ thống?
- Mỗi actor muốn đạt mục tiêu gì?
- Actor nào cần đăng nhập? Actor nào chỉ nhận thông báo?
- Vai trò nào được xem, tạo, sửa, xóa, duyệt, cấu hình?
- Có giới hạn theo chi nhánh, phòng ban, tenant, owner không?

### 3. Use Cases
- Mỗi actor làm nghiệp vụ nào để đạt mục tiêu?
- Điều gì kích hoạt use case?
- Điều kiện trước khi bắt đầu là gì?
- Luồng chính từng bước: actor làm gì, hệ thống phản hồi gì?
- Có luồng thay thế, lỗi, hủy, quay lại, phê duyệt, hết quyền, mất kết nối không?
- Kết quả thành công và dữ liệu thay đổi là gì?
- Use case nào MVP, use case nào để sau?

### 4. Features And Screens
- Danh sách feature theo nhóm chức năng là gì?
- Feature nào phục vụ use case nào?
- Màn hình nào cần có: list, detail, create, edit, approval, report, popup, tab?
- Mỗi màn hình có field nào, field nào bắt buộc, readonly, default, validate?
- Mỗi nút/action xử lý gì, tạo message gì, ghi log gì?
- Role nào được truy cập màn hình/action nào?
- Có cần mockup, responsive, import/export, search/filter/sort/pagination không?

### 5. Data
- Hệ thống quản lý entity nào?
- Mỗi entity có field gì, kiểu dữ liệu gì, bắt buộc hay tùy chọn?
- Mã nghiệp vụ tự sinh hay nhập tay?
- Quan hệ giữa entity là gì?
- Dữ liệu nào cần lịch sử, audit, xóa mềm, mã hóa, retention?
- Dữ liệu nào import/export hoặc đồng bộ từ hệ thống khác?

### 6. Business Rules
- Điều kiện nào cho phép tạo/sửa/xóa/gửi/duyệt/từ chối/hủy?
- Workflow status gồm những trạng thái nào?
- Actor nào được chuyển trạng thái nào?
- Có công thức tính, làm tròn, thuế, phí, chiết khấu, ngưỡng cảnh báo không?
- Rule nào cố định, rule nào cấu hình được?
- Khi vi phạm rule, hệ thống báo gì?

### 7. Messages
- Message thành công cho từng thao tác là gì?
- Validation message cho từng field là gì?
- Business error, permission error, system error là gì?
- Có confirm trước thao tác nguy hiểm không?
- Email/SMS/push/in-app gửi cho ai, khi nào, template nào?
- Message cần đa ngôn ngữ hoặc biến động như mã đơn, tên user, ngày hết hạn không?

### 8. Non-Functional Requirements
- Số user tổng và concurrent là bao nhiêu?
- Response time mục tiêu cho màn hình/tác vụ chính?
- Uptime yêu cầu? RPO/RTO? Backup tần suất nào?
- Dữ liệu nhạy cảm nào cần bảo vệ? Có MFA, password policy, session timeout không?
- Audit log cần lưu gì và bao lâu?
- Hỗ trợ browser/device/OS/ngôn ngữ/múi giờ/accessibility nào?
- Có monitoring, alerting, dev/staging/prod, scaling requirement không?

### 9. Integrations
- Tích hợp hệ thống nào, mục đích gì?
- Dữ liệu gửi/nhận gồm gì?
- Real-time, batch, webhook, API, file, database?
- Auth, rate limit, sandbox, retry, error handling, request/response log?
- Khi hệ thống ngoài lỗi, user thấy gì và nghiệp vụ xử lý thế nào?

### 10. Closeout
- 5 yêu cầu quan trọng nhất là gì?
- Yêu cầu nào thiếu thì không thể go-live?
- Có stakeholder/tài liệu/mẫu form/report/mockup cần bổ sung không?
- Giả định nào cần ghi? Quyết định nào còn mở?
- Ai xác nhận SRS cuối cùng?

## Traceability Template
Use this for each use case:

```text
UC-ID:
Actor:
Goal:
Feature(s):
Screen(s):
Data entity/fields:
Business rules:
Messages:
NFR impact:
Open questions/TBD:
Acceptance criteria:
```

## Interview Strategy
If stakeholder time is short, do not ask random broad questions. Pick top use cases and drill each one end-to-end, extracting actor, screen, data, rule, message, NFR, and acceptance criteria from the same story.

## Common Mistakes
| Mistake | Fix |
|---|---|
| Asking 5-10 generic questions then filling rest by assumption | Mark unknowns and schedule follow-up |
| Asking many questions but not mapping to SRS sections | Use Quick Reference and Traceability Template |
| Treating NFRs as vague words like fast/secure | Ask measurable numbers and constraints |
| Capturing screens without business rules | For each action ask allowed conditions and failure message |
| Capturing use cases without exceptions | Ask alternative, exception, permission, integration failure flows |
| Ignoring external actors | Include systems, devices, schedulers, payment/email/SMS services |

## Rationalizations
| Excuse | Reality |
|---|---|
| "Khách bận, hỏi vài câu rồi tự suy ra" | SRS needs evidence; unknowns become `TBD` or assumptions requiring approval |
| "User không biết kỹ thuật nên bỏ NFR" | Ask in plain language, then convert answers into measurable NFRs |
| "Một buổi không đủ nên hỏi generic" | Drill top use cases end-to-end; this gives better coverage than broad questions |
| "Screen list đủ để viết feature" | Screens without actions, rules, data, messages, and permissions are incomplete |
| "NFR để dev tự quyết" | BA must capture business constraints: users, uptime, data loss tolerance, security needs |

## Red Flags
- "Tự suy ra phần còn lại"
- "Hỏi vài câu thôi là đủ"
- "Không cần NFR cụ thể"
- "Chưa rõ thì cứ điền đại"
- "Screen list đủ rồi, khỏi hỏi rule"
- "Use case chỉ cần tên"

All red flags mean stop, mark `TBD`, and ask targeted follow-up.
