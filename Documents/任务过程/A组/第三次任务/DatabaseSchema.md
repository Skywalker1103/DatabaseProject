## 根据功能点的调整更新的数据库模式

#### 1. 用户表 (Users)

用户ID (UserID) [主键]

用户名 (Username)

密码 (Password)

账号类型 (AccountType)


#### 2. 花园表 (Gardens)

花园ID (GardenID) [主键]

花园名称 (GardenName)

拥有者ID (OwnerID) [外键：用户表中的UserID]

是否公开 (IsPublic)


#### 3. 花园评分表 (GardenRatings)

评分ID (RatingID) [主键]

花园ID (GardenID) [外键：花园表中的GardenID]

评分值 (RatingValue)

评分人ID (RaterID) [外键：用户表中的UserID]


#### 4. 花园评论表 (GardenComments)

评论ID (CommentID) [主键]

花园ID (GardenID) [外键：花园表中的GardenID]

评论内容 (CommentContent)

评论人ID (CommenterID) [外键：用户表中的UserID]


#### 5. 用户信息表 (UserProfile)

用户ID (UserID) [主键，外键：用户表中的UserID]

头像 (Avatar)

其他个人信息 (OtherInfo)


#### 6. 管理员表 (Admins)

管理员ID (AdminID) [主键，外键：用户表中的UserID]


#### 7. 用户登录记录表 (UserLoginHistory)

登录记录ID (LoginID) [主键]

用户ID (UserID) [外键：用户表中的UserID]

登录时间 (LoginTime)


#### 8. 花园审核记录表 (GardenApprovalHistory)

审核记录ID (ApprovalID) [主键]

花园ID (GardenID) [外键：花园表中的GardenID]

审核结果 (ApprovalResult)

审核时间 (ApprovalTime)


#### 9. 花园维护记录表 (GardenMaintenance)

维护记录ID (MaintenanceID) [主键]

花园ID (GardenID) [外键：花园表中的GardenID]

维护人ID (MaintainerID) [外键：用户表中的UserID]

维护时间 (MaintenanceTime)


#### 10. 用户统计信息表 (UserStats)

用户ID (UserID) [主键，外键：用户表中的UserID]

注册时间 (RegistrationTime)

最近登录时间 (LastLoginTime)

花园数 (GardenCount)

博客数 (BlogCount)

评分数 (RatingCount)

评论数 (CommentCount)

违规次数 (ViolationCount)

积分 (Points)


#### 11. 用户举报记录表 (UserReports)

举报ID (ReportID) [主键]

举报人ID (ReporterID) [外键：用户表中的UserID]

被举报人ID (ReportedUserID) [外键：用户表中的UserID]

被举报内容ID (ReportedContentID)

举报类型 (ReportType)

举报时间 (ReportTime)


#### 12. 举报审核记录表 (ReportApprovalHistory)

审核记录ID (ApprovalID) [主键]

举报ID (ReportID) [外键：用户举报记录表中的ReportID]

审核结果 (ApprovalResult)

审核时间 (ApprovalTime)


#### 13. 文章表 (Articles)

文章ID (ArticleID) [主键]

标题 (Title)

内容 (Content)

作者ID (AuthorID) [外键：用户表中的UserID]

发布时间 (PublishTime)


#### 14. 文章评分表 (ArticleRatings)

评分ID (RatingID) [主键]

文章ID (ArticleID) [外键：文章表中的ArticleID]

评分值 (RatingValue)

评分人ID (RaterID) [外键：用户表中的UserID]


#### 15. 文章评论表 (ArticleComments)

评论ID (CommentID) [主键]

文章ID (ArticleID) [外键：文章表中的ArticleID]

评论内容 (CommentContent)

评论人ID (CommenterID) [外键：用户表中的UserID]


#### 16. 志愿者招募表 (VolunteerRecruitment)

招募ID (RecruitmentID) [主键]

花园ID (GardenID) [外键：花园表中的GardenID]

招募者ID (RecruiterID) [外键：用户表中的UserID]

招募时间 (RecruitmentTime)

招募内容 (RecruitmentContent)


#### 17. 招募申请记录表 (ApplicationRecords)

记录ID (RecordID) [主键]

招募ID (RecruitmentID) [外键：志愿者招募表中的RecruitmentID]

申请人ID (ApplicantID) [外键：用户表中的UserID]

申请时间 (ApplicationTime)

审核结果 (ApprovalResult)


#### 18. 志愿工作记录表 (VolunteerWorkRecords)

记录ID (RecordID) [主键]

招募ID (RecruitmentID) [外键：志愿者招募表中的RecruitmentID]

志愿者ID (VolunteerID) [外键：用户表中的UserID]

工作内容 (WorkContent)

工作时间 (WorkTime)

提交时间 (SubmissionTime)


#### 19. 花园活动表 (GardenActivities)

活动ID (ActivityID) [主键]

花园ID (GardenID) [外键：花园表中的GardenID]

活动名称 (ActivityName)

活动日期 (ActivityDate)

活动详情 (ActivityDetails)


#### 20. 活动邀请表 (ActivityInvitations)

邀请ID (InvitationID) [主键]

活动ID (ActivityID) [外键：花园活动表中的ActivityID]

邀请人ID (InviterID) [外键：用户表中的UserID]

邀请时间 (InvitationTime)


#### 21. 积分商城商品表 (RewardItems)

商品ID (ItemID) [主键]

商品名称 (ItemName)

所需积分 (PointsRequired)

商品库存 (ItemStock)


#### 22. 积分兑换记录表 (RedeemRecords)

兑换记录ID (RedeemID) [主键]

用户ID (UserID) [外键：用户表中的UserID]

商品ID (ItemID) [外键：积分商城商品表中的ItemID]

兑换时间 (RedeemTime)
