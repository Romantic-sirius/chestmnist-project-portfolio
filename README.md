# ChestMNIST Portfolio Showcase

本目录是用于在线作品集展示的精简结果包（已去除模型权重）。

## 目录结构

- comparison_plots/
  - comparison_auc.png
  - comparison_val_loss.png
- vit_pretrain_off_posw_off/
- vit_pretrain_on_posw_off/
- vit_pretrain_on_posw_on/
- fair_resnet18_reg2/
- index.html
- styles.css

每个实验目录包含：
- config.json
- final_result.json
- metrics.csv
- metrics.json
- metrics_curve.png
- report.md
- gradcam/*.png
- error_analysis/errors_topk.json
- error_analysis/error_*.png

## 四组实验说明

1. vit_pretrain_off_posw_off
   - ViT，无预训练，不使用 pos_weight
2. vit_pretrain_on_posw_off
   - ViT，使用预训练，不使用 pos_weight
3. vit_pretrain_on_posw_on
   - ViT，使用预训练，使用 pos_weight
4. fair_resnet18_reg2
   - ResNet18，使用预训练，使用 pos_weight

## 结果解读建议

1. 先看 comparison_plots/comparison_auc.png：比较四组整体 AUC。
2. 再看 comparison_plots/comparison_val_loss.png：比较四组稳定性与收敛趋势。
3. 每组看 metrics_curve.png：观察 train/val 曲线是否出现过拟合。
4. 每组看 gradcam/：检查模型关注区域是否合理。
5. 每组看 error_analysis/：分析高错误样例模式（漏检/过检）。

## 发布方式

- 本目录可直接上传到 GitHub 仓库并启用 GitHub Pages。
- 入口页面：index.html

## 备注

- 本目录不包含 .pth 权重文件，以减小体积，适合网页展示。
- 若需完整复现训练，请使用原始项目目录。
