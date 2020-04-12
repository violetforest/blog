---
layout: post
title:  "Street Photography in the Age of Online Privacy"
categories: photography, privacy, computer vision
---
![Google Photos face recognition](./../assets/images/2.jpg)

In the times of quarantine, I found the need to go for a long walk. During that time, I also had a the urge to take photographs of people on the streets, enjoying whatever sunshine they could get after 1 month of lockdown. It's not every day that a pandemic happens, and I wanted to photograph it.

My phone's back-facing camera's lens is broken, so I shoot with the front-facing camera, which takes my stealth and framing-control down a couple of levels. After clumsily taking photographs of people on the street, I passed by a young couple sitting, awkwardly snapped their photo, and kept walking. I had a feeling the woman saw me, and sure enough, I heard her chasing behind me. Stunned yet defensive, I kept walking, acting stupid. I obviously knew what she wanted. She caught up to me, while another stranger tried to intervene, and kept yelling "Why did you take my photo?!".

She had asked me to delete it, but I knew I had a right to take her photograph in public. Street photographers and documentary photographs have different ways of dealing with the issue of invasion of privacy. Some photographers choose an aggressive style of shooting, keeping a "Shoot first, apologize later" attitude. There's always a balance between the law, morale and your artistic ego, and in between all of that, is a stranger's right to privacy. As I walked home, I couldn't decide: Should I delete the photo or not?

After pondering about how what I had taken from her with my phone's camera, I realized something that complicated the matter even more: the image I just took was most likely already automatically uploaded to my Google Photos. And I realized that with today's technology, taking a digital photograph doesn't just steal someone's image, it can also steal their digital privacy.

I had just given her face to Google without her consent, and I knew Google was going to run a face recognition algorithm on the photograph. According to Google's website, its not only the face that is scanned, its also the clothing that is analyzed, in its "Face Grouping" feature:

>"We detect whether any photo has a face in it.
If the face grouping feature is turned on, algorithmic models are used to predict the similarity of different images and estimate whether 2 images represent the same face.
Photos that are likely to represent the same face are grouped together...
When face grouping is on, Google Photos may also include photos in a particular group based on other characteristics. This includes photos being taken close together in time and detecting that a person is wearing the same clothing across photos when a face is not visible." -[source](https://support.google.com/photos/answer/6128838?hl=en)

So although others users can't access these face groupings, the photograph is exposed to not just humans, but also computer vision. On top of that, it is stored in Google's memory:

>"We also collect the content you create, upload, or receive from others when using our services. This includes things like email you write and receive, photos and videos you save, docs and spreadsheets you create, and comments you make on YouTube videos." -[source](https://policies.google.com/privacy?hl=en-US)

The time, date, and GPS coordinates of the photograph were also uploaded with the photograph in the EXIF data. Although this data is reportedly delete when uploading to social media platforms, it is not deleted when sharing to your own website, like a blog.

![Google Photos shows EXIF data](./../assets/images/1.jpg)

 Even more, if I publish this photograph on my website, and it is indexed by Google's or a social media platform, there is a chance it could be scraped and added to a databases like that of Clearview AI's, where it could be used to create a profile of this person, and this profile dataset could be searched by anyone with access to the database.

I decided that, to protect the woman's identity from not only human vision but also computer vision, I would publish the photo with the EXIF data removed and the face blurred out, only as an addition to this blog post for visual purposes. I don't think any of this metadata was in this woman's mind when she was demanding that I give part of her identity back -- but the more I think about it, the more I realize that photographs aren't just the visual data they used to be, but also the metadata they contain. Even worse, when we analyze this visual data with facial recognition algorithms, and mix it with the metadata, we can aggregate patterns of behavior and relationships. This isn't exactly new information, but when seen from the angle of the relationships between a street photographer and a stranger, you realize you're taking more from them than originally thought.
