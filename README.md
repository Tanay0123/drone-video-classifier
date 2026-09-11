# drone-video-classifier
2D Convolutional Neural Network for a video classification

Motivation:

RedKite Aerospace Australia as a drone-manufacturing startup, that is seeking a contract from a regional emergency-services provider.

The provider's request for proposal (RFP) is for a drone capable of delivering time-critical medical supplies, while also being capable of following marshalling-style gestures from the person receiving the supplies.

RedKite is therefore motivated to build a gesture-classifier for their drone platform. The onboard perception stack within the drone platform already has a segmenter, that first watches the reciever perform a gesture, and then extracts a five-frame instance.

Therefore, the classifier must be able to predict which of the 13 gestures a given 5-frame instance belongs to.

Constraints:

2D convolutional backbones only. No recurrent models, no 3D convolutions, and no temporal-attention / video-transformer architectures.
The model must run inference on one instance at a time on an embedded board, ensuring the operation is small enough that a real-time operation on a constrained hardware is plausible.
ImageNet-pretrained backbones and standard augmentation are permitted. But pretraining on external gesture or action-recognition datasets is not allowed.

Dataset Summary:

Small, unbalanced dataset with 11 distinct subjects, performing 13 distinct gestures, in mostly uniform, uncluttered backgrounds. Each "gesture" is represented as five keyframes, that were extracted from a video sample. 

Model Summary:

Transfer-Learning with a ResNet-18 backbone and fine-tuning, augmentation, weight-balanced cross-entropy loss.
Developed using PyTorch environment. 

(The described scenario represents the context for a university assignment; all entities mentioned are fictitious)
