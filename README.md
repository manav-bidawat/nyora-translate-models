# nyora-translate-models

Nyora's mirror of the on-device models used by the in-browser page translator
(`nyora-web` → `core/translate/tl-worker.js`) and nothing else.

**These are not Nyora's models.** Every file here is an unmodified copy of a
third-party release, mirrored so the browser download does not depend on another
provider's hosting, rate limits or availability. Upstream is listed for each file
below; all of them are Apache-2.0.

Files are served to the app straight from `raw.githubusercontent.com`, pinned to
a commit — a future model change gets a new URL and therefore a new browser cache
key, so it can never silently replace bytes already on someone's device.

## Contents

| Path | Bytes | Upstream | Licence |
|---|---:|---|---|
| `detector/yolo26n.onnx` | 6,069,760 | [Kiuyha/Manga-Bubble-YOLO](https://huggingface.co/Kiuyha/Manga-Bubble-YOLO) @ `fb64650` | Apache-2.0 |
| `manga-ocr/encoder_model_uint8.onnx` | 86,967,805 | [onnx-community/manga-ocr-base-ONNX](https://huggingface.co/onnx-community/manga-ocr-base-ONNX) @ `f902340` | Apache-2.0 |
| `manga-ocr/decoder_model_uint8.onnx` | 29,627,952 | [onnx-community/manga-ocr-base-ONNX](https://huggingface.co/onnx-community/manga-ocr-base-ONNX) @ `f902340` | Apache-2.0 |
| `manga-ocr/vocab.txt` | 24,072 | [kha-white/manga-ocr-base](https://huggingface.co/kha-white/manga-ocr-base) @ `aa6573b` | Apache-2.0 |
| `paddle/PP-OCRv5_mobile_det.onnx` | 4,826,518 | [PaddlePaddle/PP-OCRv5_mobile_det_onnx](https://huggingface.co/PaddlePaddle/PP-OCRv5_mobile_det_onnx) @ `e6f4fa8` | Apache-2.0 |
| `paddle/PP-OCRv6_small_rec.onnx` | 21,159,378 | [ogkalu/ppocr-v6-onnx](https://huggingface.co/ogkalu/ppocr-v6-onnx) @ `8caf024` | Apache-2.0 |
| `paddle/PP-OCRv6_small_rec.txt` | 74,947 | [ogkalu/ppocr-v6-onnx](https://huggingface.co/ogkalu/ppocr-v6-onnx) @ `8caf024` | Apache-2.0 |
| `paddle/korean_PP-OCRv5_mobile_rec.onnx` | 13,418,787 | [PaddlePaddle/korean_PP-OCRv5_mobile_rec_onnx](https://huggingface.co/PaddlePaddle/korean_PP-OCRv5_mobile_rec_onnx) @ `5c6f574` | Apache-2.0 |
| `paddle/ppocrv5_korean_dict.txt` | 47,451 | [PaddlePaddle/PaddleOCR](https://github.com/PaddlePaddle/PaddleOCR) @ `0a8a635` | Apache-2.0 |

Two upstream files are both named `inference.onnx`; they are renamed here to say
which model they are. Contents are byte-identical to upstream — see `SHA256SUMS`.

## Verifying

    shasum -a 256 -c SHA256SUMS

The digests are the upstream files' own, recorded at mirror time
(2026-07-27). Nothing in this repo has been re-exported, quantised or converted.

## Git LFS

Deliberately **not** used. `raw.githubusercontent.com` serves an LFS pointer file
rather than the object, which would hand the app a 130-byte text file where it
expects an ONNX graph. Every file here is under GitHub's 100 MB limit as a plain
blob.
