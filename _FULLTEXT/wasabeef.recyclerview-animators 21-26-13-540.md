recyclerview animators recyclerview animators is an android library that allows developers to easily create recyclerview with animations please feel free to use this features animate addition and removal of itemanimator appearance animations for items in recyclerview adapter demo itemanimator adapters samples how do i use it setup gradle on your modules build gradle file add this implementation statement to the dependencies section groovy dependencies implementation jp wasabeef recyclerview animators 2 3 0 also make sure that the repositories section includes not only jcenter but also a maven section with the google endpoint repositories jcenter google itemanimator step 1 set recyclerview itemanimator java recyclerview recyclerview recyclerview findviewbyid r id list recyclerview setitemanimator new slideinleftanimator java recyclerview recyclerview recyclerview findviewbyid r id list slideinupanimator animator new slideinupanimator new overshootinterpolator 1f recyclerview setitemanimator animator step 2 please use the following notifyitemchanged int notifyiteminserted int notifyitemremoved int notifyitemrangechanged int int notifyitemrangeinserted int int notifyitemrangeremoved int int if you want your animations to work do not rely on calling notifydatasetchanged as it is the recyclerviews default behavior animations are not triggered to start inside this method java public void remove int position mdataset remove position notifyitemremoved position public void add string text int position mdataset add position text notifyiteminserted position advanced step 3 you can change the durations java recyclerview getitemanimator setaddduration 1000 recyclerview getitemanimator setremoveduration 1000 recyclerview getitemanimator setmoveduration 1000 recyclerview getitemanimator setchangeduration 1000 advanced step 4 change the interpolator java slideinleftanimator animator new slideinleftanimator animator setinterpolator new overshootinterpolator or recyclerview setitemanimator new slideinupanimator new overshootinterpolator 1f recyclerview setitemanimator animator advanced step 5 by implementing animateviewholder you can override preset animation so custom animation can be set depending on view holder java static class myviewholder extends recyclerview viewholder implements animateviewholder public myviewholder view itemview super itemview override public void preanimateremoveimpl recyclerview viewholder holder override public void animateremoveimpl recyclerview viewholder holder viewpropertyanimatorlistener listener viewcompat animate itemview translationy itemview getheight 0 3f alpha 0 setduration 300 setlistener listener start override public void preanimateaddimpl recyclerview viewholder holder viewcompat settranslationy itemview itemview getheight 0 3f viewcompat setalpha itemview 0 override public void animateaddimpl recyclerview viewholder holder viewpropertyanimatorlistener listener viewcompat animate itemview translationy 0 alpha 1 setduration 300 setlistener listener start animators cool landinganimator scale scaleinanimator scaleintopanimator scaleinbottomanimator scaleinleftanimator scaleinrightanimator fade fadeinanimator fadeindownanimator fadeinupanimator fadeinleftanimator fadeinrightanimator flip flipintopxanimator flipinbottomxanimator flipinleftyanimator flipinrightyanimator slide slideinleftanimator slideinrightanimator overshootinleftanimator overshootinrightanimator slideinupanimator slideindownanimator recyclerview adapter step 1 set recyclerview itemanimator java recyclerview recyclerview recyclerview findviewbyid r id list myadapter adapter new myadapter recyclerview setadapter new alphainanimationadapter adapter advanced step 2 change the durations java myadapter adapter new myadapter alphainanimationadapter alphaadapter new alphainanimationadapter adapter alphaadapter setduration 1000 recyclerview setadapter alphaadapter advanced step 3 change the interpolator java myadapter adapter new myadapter alphainanimationadapter alphaadapter new alphainanimationadapter adapter alphaadapter setinterpolator new overshootinterpolator recyclerview setadapter alphaadapter advanced step 4 disable the first scroll mode java myadapter adapter new myadapter alphainanimationadapter alphaadapter new alphainanimationadapter adapter alphaadapter setfirstonly false recyclerview setadapter alphaadapter advanced step 5 multiple animations java myadapter adapter new myadapter alphainanimationadapter alphaadapter new alphainanimationadapter adapter recyclerview setadapter new scaleinanimationadapter alphaadapter adapters alpha alphainanimationadapter scale scaleinanimationadapter slide slideinbottomanimationadapter slideinrightanimationadapter slideinleftanimationadapter applications using recyclerview animators please ping me or send a pull request if you would like to be added here icon application ameba ownd quitnow abematv developed by daichi furiya wasabeef dadadada chop gmail com contributions any contributions are welcome contributers craya1982 thanks inspired by androidviewanimations in daimajia license copyright 2018 wasabeef licensed under the apache license version 2 0 the license you may not use this file except in compliance with the license you may obtain a copy of the license at http www apache org licenses license 2 0 unless required by applicable law or agreed to in writing software distributed under the license is distributed on an as is basis without warranties or conditions of any kind either express or implied see the license for the specific language governing permissions and limitations under the license