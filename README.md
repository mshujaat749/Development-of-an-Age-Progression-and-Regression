# Development-of-an-Age-Progression-and-Regression

This project performs age progression and regression using deep learning techniques. It allows users to upload an image and generate a video showing age transformations over time.

## 🎯 Features

- **Age progression and regression** for input images
- Realistic and smooth transitions between different age stages
- Supports both male and female models
- Generates output videos in both `mp4` and `webm` formats

## 🛠️ Technologies Used

- [Python](https://www.python.org/)
- [PyTorch](https://pytorch.org/)
- [OpenCV](https://opencv.org/)
- [Google Colab](https://colab.research.google.com/)

## 📋 Requirements

- Python 3.x
- Required Python packages (`torch`, `opencv-python`, etc.)
- Google Colab (for cloud execution)


## 🚀 Usage

1. Download the required models:
   ```bash
   python download_models.py
   ```
2. Run the script using Google Colab or your local environment:
   - Upload your image (supports only a single image at a time)
   - Modify `opt.name` to switch between male and female models (`males_model` or `females_model`)

3. After generating the video, download the results from the `results` directory.

## 🔑 Key Code Snippets

### Initializing the Model
```python
opt.name = 'females_model'  # Change to 'males_model' for male image transformations
model = create_model(opt)
model.eval()
```

### Processing the Image
```python
data = dataset.dataset.get_item_from_path(img_path)
visuals = model.inference(data)
```

### Creating the Video
```python
visualizer.make_video(visuals, out_path)
```

## 📂 Directory Structure

```
/your-repo
│
├── download_models.py       # Script to download required models
├── main_script.py           # Main age progression and regression script
├── results/                 # Output videos
├── README.md                # Project documentation
└── requirements.txt         # Required packages
```

## 🤝 Contributing

Contributions are welcome! Feel free to check the [issues page](../../issues/) for any open issues or feature requests.

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
