# Image-Editing-via-controllable-GANs
Re-implementation and enchancement of the paper ‘Enjoy your editing: Controllable GANs for image editing via Latent Space Navigation’. \
**Team members** \
Sanika Padegaonkar (20D070069) \
Sanket Potdar (20D070070) \
Simran Tanwar (20D070078) \
**Official Github repository** : https://github.com/KelestZ/Latent2im/tree/main \
**Our modifications** 
1) Fixed a bug in the file train_options.py.
The original code was giving an error because the Namespace ‘opt’ did not have certain attributes. After trying multiple things we realised that the missing attributes were present in another attribute of the Namespace ‘opt’ called ‘options’. Combining the two namespaces fixed the problem. The following code was added after line 186
opts = argparse.Namespace(**args)
dict_opt = vars(opt)
dict_opt.update(vars(opt.options))
opt = argparse.Namespace(**dict_opt)
2) Tried a different face regressor module. The official implementation used resnet50 while we tried it with mobilenetv2. The fine-tuning notebook as well as the final model used for mobilenetv2 have been uploaded in the drive link.
3) Added LR scheduler to the optimization process. Relevant code has been added to the optimizeParametersAll() function of the file transform_base.py in the sub-folder stylegan_v2_real in the folder graphs.
4) Experimented with different batch sizes and num_samples.
5) Experimented with natural images.
More details on points 2), 3), 4) and 5) are provided in the report
The official github implementation has also been cited in the report
