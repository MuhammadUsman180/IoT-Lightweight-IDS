# Lightweight Deep Learning Intrusion Detection System for IoT-Enabled Smart Homes  
**Final Year Project – HITEC University Taxila (2023)**  
**Supervisor:** Dr. Hasna Arshad (Assistant Professor, Department of Computer Science)  
**Author:** Muhammad Usman – usman55340@gmail.com  
**LinkedIn:** https://linkedin.com/in/muhammadusman032  
**Current position:** IT Security Administrator @ SPARROW EMR Inc., PIMS Hospital Islamabad

## Achievement Summary
- Detection accuracy: **99.8%+** overall on Edge-IIoTset dataset  
- Model size: **< 10 MB** (after quantization)  
- RAM usage on inference: **< 50 MB**  
- Designed to run in real-time on ESP32 / Raspberry Pi Zero  
- Zero false positives on normal traffic  
- Manuscript finalised – submission planned to **IEEE Internet of Things Journal** (Q1) in 2026

## Abstract
The massive adoption of IoT devices in smart homes has brought convenience but also massive cybersecurity risks (MitM, DDoS, SQL Injection, Password attacks, etc.). Traditional heavy-weight security solutions (deep encryption, full firewalls) are impossible on resource-constrained devices.

This project proposes a **lightweight hybrid deep learning IDS** combining:
- 1D-CNN
- Bi-LSTM
- Multi-Head Self-Attention

The model achieves >99.8% detection accuracy while keeping model size under 10 MB and memory footprint under 50 MB through quantization and knowledge distillation. An adaptive feature selection module reduces input to only **10 most critical features**, enabling real-time deployment on microcontrollers like ESP32.

The system maintains **0% False Alarm Rate** on normal traffic and shows outstanding performance on common attacks, making it ideal for real-world smart home and healthcare IoT protection.

## Dataset
Edge-IIoTset (2022) – 2+ million records, 15 attack types + normal traffic  
Link: https://ieee-dataport.org/documents/edge-iiotset-new-comprehensive-realistic-cyber-security-dataset-iot-and-iiot-applications

## Folder Structure
├── model/                  # Trained models (.h5 and quantized .tflite)
├── notebooks/              # Jupyter notebooks with experiments
├── src/                    # Main Python scripts (training, inference, feature selection)
├── dataset/              # Sample data (full dataset too large for GitHub)
├── results/                # Graphs, confusion matrices, performance reports
├── FYP_Report.pdf          # Complete thesis (60+ pages)
└── requirements.txt

## Quick Start (Inference on PC)
```bash
pip install -r requirements.txt
python src/inference.py --model model/lightweight_ids_quantized.tflite --pcap samples/normal_traffic.pcap
