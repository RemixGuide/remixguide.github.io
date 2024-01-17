---
title: Remix Guide Main
layout: template
filename: README.md
--- 


### An RTX Remix asset guide for dummies  
Want to see something added or discussed in this document? Poke @Traggey or @Runestorm on the [RTX Remix Showcase](https://discord.gg/rtxremix) discord.

# Remix Asset Guidelines

Remix utilises a PBR based texturing workflow
PBR stands for Physically Based Rendering, and is a combination of a bunch of really neat techniques that help create more cohesive and realistic results.
In order to create PBR assets we first need to understand the basics of what PBR entails, this might seem spooky and overwhelming at first but it’s honestly rather simple once you try it out a few times!
To explain the very basic concepts and most important aspects of PBR based rendering, I’ve put together a few demonstrations of the two most important aspects that new users might have a hard time wrapping their head around.

So let’s start with what the roughness value is, roughness can in simple terms be described as “How shiny” an object is, the higher the roughness value of the surface is, the less shiny it will be, think of it as a gravel road, that’s very rough, not very shiny! Whilst something not very rough, like glass and water is indeed, very shiny!

![](https://lh7-us.googleusercontent.com/qkr2B1aIRlSvhQPx0H-0hE--bbAik0BPp_ouDo1p08Omc7BZMMNd_uQW_9XPcESgAgreMA_3_XxA_IesGuWdxYTsHMwaznuTG0Al7CynO65FUTKiryMCxSBR7FCOF8PFqrZUkkD2kGSLJSRzMM2_tYs)  

After roughness, we have metallic, otherwise commonly called “Metalness” this value determines where on your texture a metallic surface is located, with white indicating full metallic, and black non metallic, typically speaking in the realm of realism no material ever has a value that is anything other than 0 or 1, a material is either metal, or it isn’t.

However, non 0 or 1 values are still commonly used as they are the best way simulate things like fine grain dirt and dust on top of a metallic surface as the actual texture resolution required to make every single grain of dirt have an accurate value assigned is not really possible, so be careful with how you use this value when combined with gradients of any kind, a thin layer of dust on metal could for example be represented by a 0.9 or 0.8 value, instead of 1.

So the proper way to use these values, is essentially, if a surface isn’t metal like for example wood or plastic, then the area should be black or “0” in the texture, whereas if it IS made out of metal, like steel, silver, gold or iron, then you’ll want the texture to be white for a value of “1”

![](https://lh7-us.googleusercontent.com/uRvF8tP-o-HzBtPLFgjFrCXRwSgui6jUOKNVwYZyHgZsEKZFCi81uHW6PeGsYqPcWPnfiEQVBb_jUCW0ZmEPPh9q22FOGgqhkUgiqw-9eiIsBs_AW5tq14SS9uPTr4Iym27Cxrvgc1Qo4Ygehw8mVy8)  

Naturally Roughness and Metallic are separated from one another, driven by their own textures which means that they can be combined with one another, this is how we create materials like shiny and dull metal, and various plastics!

![](https://lh7-us.googleusercontent.com/rGAJ1P3uqMUSlNY9XGM6BjO_f_CW0Fg42SiSp_z32oxgPs-UaCNLTQ2JNec_x2aKMhCvWYQNXcrvtJv7Sb9UfnXyLxuTHb2pLf07VlVQH5Uj7tAHxAI66sNdbn4Fj_tL1tWAZ6g7nBQa8tp-t6fFah4)

The following texture maps are used in the Remix PBR workflow.
Albedo - This is the basic colour information of the material, should contain no light or shadow information
Roughness - This texture defines how rough/smooth a surface is, black being smooth and more reflective, white being rough and dull
Metallic/Metalness - As the name would specify, this texture defines where surfaces with metallic properties are on your material
Normal - This texture contains directional information used by the engine to fake lighting and details across a surface
Height - This texture is used in a POM calculation ( Parallax occlusion mapping ) and fakes depth in your material
SSS - SubSurfaceScattering textures tell the engine when a surface is allowed to transmit light through it, think of a thin lampshade or human skin
Opacity - These textures are black and white masks that render the surface invisible or visible in areas, is used to make holes or cut out leaves

See below thread for a more detailed breakdown on the usage of these textures
( We’ll probably just add this information to this document later )
https://discord.com/channels/1028444667789967381/1111273025657114654/1111273025657114654


# Authoring Models

Models are models and should be modelled using modelling tools that are used to create models. But not the photo model kind, you’ll need a camera for that.  
  
Remix is generally very good at handling high polygon counts, whilst it’s always a good idea to make sure you don’t go bananas you also generally don’t have to worry too much about pure polycounts! If adding a few extra triangles greatly improves the look of your work, it’s usually safe to go for it.


# Software List

List of software used for asset creation, now with links!  
  
It’s important to note that the software one decides to use is purely up to personal preference, all tools come with their own pros and cons, try different tools out and see what works for you! ( Looking at you blender cult! )

##   
3D modelling

- [Autodesk Maya](https://www.autodesk.com/products/maya/overview?term=1-YEAR&tab=subscription) - 3D modelling tool - Paid
    
- [Autodesk 3D’s max](https://www.autodesk.com/products/3ds-max/overview?term=1-YEAR&tab=subscription) - 3D modelling tool - Paid
    
- [Blender](https://www.blender.org/) (Stinky) - 3D modelling tool - Free
    
- [C4D](https://www.maxon.net/en/cinema-4d) - 3D modelling tool - Paid
    
- [MODO](https://www.foundry.com/products/modo) - 3D modelling tool - Paid
    
- [Houdini](https://www.sidefx.com/products/houdini/) - Procedural 3D modelling and effects tool - Paid
    
- [3Dcoat](https://3dcoat.com/) - Modelling, sculpting and texturing tool - Paid

## 3D sculpting

- [Zbrush](https://www.maxon.net/en/zbrush) - Highpoly sculpting tool - Paid
    
- [Mudbox](https://www.autodesk.com/products/mudbox/overview?term=1-YEAR&tab=subscription) - Highpoly sculpting tool - Paid
    
- [Sculptris](https://www.sculpteo.com/en/glossary/sculptris-definition/) - Highpoly sculpting tool - Free
    
- [3Dcoat](https://3dcoat.com/) - Modelling, sculpting and texturing tool - Paid

## 3D texturing

- [3Dcoat](https://3dcoat.com/) - Modelling, sculpting and texturing tool - Paid
    
- [Quixel Mixer](https://quixel.com/mixer) - Material texturing/Blending tool - Free ( Can be used without megascans )
    
- [Substance Painter](https://store.steampowered.com/app/2718190/Substance_3D_Painter_2024/) - 3D texture painting and smart materials - Paid
    
- [ArmorPaint](https://armorpaint.org/) - Node based 3D texture painting tool - Paid (Free if compiled from [Github](https://github.com/armory3d/armortools/tree/main/armorpaint))

## 2D painting/editing/texturing

- [KRITA](https://krita.org/en/) - 2D illustration and image editing tool - Free
    
- [Photoshop](https://www.adobe.com/products/photoshop.html) - 2D illustration and image editing tool - Paid
    
- [Gimp](https://www.gimp.org/) - 2D illustration and image editing tool - Free
    
- [Paint.net](https://www.getpaint.net/) - 2D illustration and image editing tool - Free
    
- [Clip Studio Paint](https://www.clipstudio.net/en/) - 2D illustration and image editing tool - Paid
    
- [Affinity Designer](https://affinity.serif.com/en-us/designer/) - A 2D vector tool, perfect for creating signs, stickers, logos etc. - Paid

## Material Authoring/Generation

- [Quixel Mixer](https://quixel.com/mixer) - Material texturing/Blending tool - Free ( Can be used without megascans )
    
- [Substance Designer](https://store.steampowered.com/app/2718200/Substance_3D_Designer_2024/) - Node based material generation - Paid
    
- [InstaMAT](https://instamaterial.com/) - Very diverse material generation suite - Free limited licence, paid.
    
- [AwesomeBump](https://github.com/kmkolasinski/AwesomeBump) - A rather old normal and height map generation tool - Free, FOSS
    
- [Materialize](https://boundingboxsoftware.com/materialize/) - An image to material conversion tool - Free

## Photogrammetry

- [Substance Sampler](https://steamcommunity.com/app/2200000) - Performs Photogrammetry processing - Paid
    
- [Reality Capture](https://www.capturingreality.com/) - Performs Photogrammetry processing - Paid

## Baking Tools

- [Xnormal](https://xnormal.net/) - Texture map baking - Free ( The old UI scares people but the tool is superb )
    
- [Marmoset Toolbag](https://marmoset.co/toolbag/) - Texture map baking - Paid
    
- [Substance Painter](https://store.steampowered.com/app/2200000/Substance_3D_Sampler_2024/) - 3D texture painting and smart materials ( It bakes too ) - Paid

## Others

- [TreeIt](https://store.steampowered.com/app/2386460/Tree_It/) - Vegetation/Foliage/Tree creation tool - Free
    
- [SpeedTree](https://store.speedtree.com/) - Vegetation/Foliage/Tree creation tool - Paid
    
- [Marvelous Designer](https://www.marvelousdesigner.com/) - Clothing creation and simulation tool - Paid

# Resource List

List of resources available for remixers.  
IMPORTANT  
Make sure that when you’re using premade resources from anywhere that the distribution licence allows you to redistribute, you don’t want to end up getting sued over a mod.  
Always read up on what a licence for those assets entails, when asked for attribution, always attribute!

( Thank you Kim for compiling many of these )

- [Google Fonts](https://fonts.google.com/) - Royalty free fonts to use in your project.
    
- [Polyhaven](https://polyhaven.com/) - Royalty free HDRI, texture and model assets.
    
- [Textures.com](https://www.textures.com/) - Large library of textures and PBR materials, some free content.
    
- [AmbientCG](https://ambientcg.com/) - 3D, Textures, HDRI.
    
- [Highend3D](https://www.highend3d.com/downloads) - BROKEN WEBSITE?
    
- [AMD MaterialX Library](https://matlib.gpuopen.com/main/materials/all) - PBR materials.
    
- [CGbookcase](https://www.cgbookcase.com/) - Free PBR materials and textures.
    
- [ShareTextures](https://www.sharetextures.com/) - Free PBR materials and models.
    
- [Pixel Furnace](https://textures.pixel-furnace.com/) - Free PBR materials.
    
- [Blenders free textures](https://cloud.blender.org/p/textures/) - A non-PBR texture library.
    
- [TextureCan](https://www.texturecan.com/) - Free PBR materials.
    
- [TextureNinja](https://texture.ninja/) - Free non PBR textures.
    
- [Cc0-textures](https://cc0-textures.com/) - Free materials.
    
- [3dtextures](https://3dtextures.me/) - Free PBR materials.
    
- [Publicdomaintextures](https://publicdomaintextures.com/) - Free PBR materials.
    
- [Freepbr](https://freepbr.com/) - Free PBR materials
    
- [Devassets](https://devassets.com/) - Free various development assets
    
- [Megascans](https://quixel.com/megascans/) - Massive PBR scans library, materials and Models - Only free if using unreal engine, otherwise you must pay, even for the “Free” distributed megascans assets.
    
-
