My discord is scouter407.

Remember, the lighting will never be perfect in Arma because of the wide variety of lighting scenarios, if it looks good in default clear sky Stratis lighting, then it should in theory look good everywhere else. I would suggest downloading the RVMat I have provided as a good example of what to do for textures, feel free to use it as a base.

CO Map:

Base color, darken or lighten stuff depending on how it looks in game, because some colors just don't look good the way Arma lighting is set up, unsure how to fix this yet.

CA Map:

Base color, same idea as above but this texture map has an opacity channel in the alpha.

AS Map:

Ambient Occlusion/Shadows, follows the same idea as modern Ambient Occlusion maps, but the red channel is full white, the green channel is the ambient occlusion, and the blue channel is white.

SMDI Map:

Red channel is pure white, it's unused. 

Blue is metallic. metallic channels determine the actual material properties, so like a full white texture will be all metal, whereas a full black texture will be all non-metal. The look of the metallic is heavily determined by the RVMat settings, but some good ones to start with for a shiny metal are as follows:

`specular[] = {0.25,0.25,0.25,1};
specularPower = 80;`

To explain this, the specular is set at 0.25 as to not cause too much blown out colors with absurd levels of shine, but instead, to make it more metallic, the specular power is higher causing a tighter and more coherent surface reflection. The next important settings are the Fresnel material properties, which also influence the look of the metal. Follow the guide on the Arma 3 Super Shader wiki for the numbers to use, they are based on real life measurements and you should tweak them from there by small increments until you get what you like, but they are a good start.

Now, let's say you have a metal and a non-metal on the same RVMat, you might ask how do I get the non-metal to have shine but not be as shiny as the metal. This is where you have to go against PBR texturing, and slightly increase the metallic value of the non-metal part. It will give it the shine, but not as much shine as the metal part has.
 
Green is glossiness. White is extremely shiny, black is dull. This applies under the metallic mask on the blue channel, so make sure whatever you want to be shiny also has a metallic value.

NOHQ Map:
Normal map, DirectX format, nothing complex or weird here. Avoid using extreme values for your normal or height mapping, as it can cause pixilation in the texture when you look at in game and very strange lighting.
