## 表的设计

一个比较粗糙的设计，待优化。

#### 1. user_info - 存储用户信息
user_id (primary key)
username
password
email
user_type

#### 2. garden_info - 存储花园信息
garden_id (primary key)
user_id (foreign key to user_info)
garden_name
description
is_public
status (e.g., pending, approved, rejected)

#### 3. garden_rating - 存储花园的评分
rating_id (primary key)
garden_id (foreign key to garden_info)
user_id (foreign key to user_info)
rating_value

#### 4. garden_comment - 存储花园的评论
comment_id (primary key)
garden_id (foreign key to garden_info)
user_id (foreign key to user_info)
comment_content
rating_value

#### 5. report - 存储举报信息
report_id (primary key)
comment_id (foreign key to garden_comment)
reporter_id (foreign key to user_info)
reason

#### 6. volunteer_recruitment - 存储志愿者招募信息
recruitment_id (primary key)
garden_id (foreign key to garden_info)
user_id (foreign key to user_info)
title
description
requirements
status (e.g., pending, approved, rejected)

#### 7. volunteer_application - 存储志愿者申请信息
application_id (primary key)
recruitment_id (foreign key to volunteer_recruitment)
user_id (foreign key to user_info)
status (e.g., pending, approved, rejected)

#### 8. volunteer_work - 存储志愿工作记录
work_id (primary key)
recruitment_id (foreign key to volunteer_recruitment)
user_id (foreign key to user_info)
work_content
work_time

#### 9. reward_item - 存储奖励物品信息
item_id (primary key)
item_name
item_description
required_points

#### 10. user_reward - 存储用户奖励信息
reward_id (primary key)
user_id (foreign key to user_info)
item_id (foreign key to reward_item)
status (e.g., pending, approved, rejected)

#### 11. garden_maintenance - 存储花园维护工作记录
maintenance_id (primary key)
garden_id (foreign key to garden_info)
user_id (foreign key to user_info)
maintenance_content
maintenance_time

#### 12. maintenance_comment - 存储花园维护工作的评论
comment_id (primary key)
maintenance_id (foreign key to garden_maintenance)
user_id (foreign key to user_info)
comment_content
rating_value

