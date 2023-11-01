### waves over lambda
## Objetivo

## Solución 
```shell
Esta vez, no pudimos buscar una palabra de texto plano como picoCTF, ya que la bandera no tiene el formato habitual. Por suerte, podemos utilizar una herramienta como DCODE para solucionar esto. Nuestra primera suposición para un método de cifrado por sustitución es la sustitución monoalfabética, en la que cada carácter se reemplaza por otros caracteres. DCODE tiene un método de descifrado automático que busca mensajes coherentes en inglés y nos proporciona nuestra bandera.

israelga-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 43522
-------------------------------------------------------------------------------
dxwmoeyt pkok ft axzo rqem - rokhzkwda_ft_d_xlko_qensie_xmrnezwoer
-------------------------------------------------------------------------------
skyckkw zt ypkok cet, et f pelk eqokeia tefi txnkcpkok, ypk sxwi xr ypk tke. sktfikt pxqifwm xzo pkeoyt yxmkypko ypoxzmp qxwm vkofxit xr tkveoeyfxw, fy pei ypk krrkdy xr nejfwm zt yxqkoewy xr kedp xypko't aeowtewi klkw dxwlfdyfxwt. ypk qecakoypk skty xr xqi rkqqxctpei, skdeztk xr pft newa akeot ewi newa lfoyzkt, ypk xwqa dztpfxw xw ikdj, ewi cet qafwm xw ypk xwqa ozm. ypk eddxzwyewy pei soxzmpy xzy eqokeia e sxg xr ixnfwxkt, ewi cet yxafwm eodpfykdyzoeqqa cfyp ypk sxwkt. neoqxc tey doxtt-qkmmki ofmpy ery, qkewfwm emefwty ypk nfuukw-nety. pk pei tzwjkw dpkkjt, e akqqxc dxnvqkgfxw, e tyoefmpy sedj, ew etdkyfd etvkdy, ewi, cfyp pft eont ioxvvki, ypk veqnt xr pewit xzyceoit, oktknsqki ew fixq. ypk ifokdyxo, teyftrfki ypk ewdpxo pei mxxi pxqi, neik pft cea ery ewi tey ixcw enxwmty zt. ck kgdpewmki e rkc cxoit qeufqa. erykoceoit ypkok cet tfqkwdk xw sxeoi ypk aedpy. rxo txnk oketxw xo xypko ck ifi wxy skmfw ypey menk xr ixnfwxkt. ck rkqy nkifyeyflk, ewi rfy rxo wxypfwm szy vqedfi tyeofwm. ypk iea cet kwifwm fw e tkokwfya xr tyfqq ewi kghzftfyk sofqqfewdk. ypk ceyko tpxwk vedfrfdeqqa; ypk tja, cfypxzy e tvkdj, cet e skwfmw fnnkwtfya xr zwtyefwki qfmpy; ypk lkoa nfty xw ypk kttkg neotp cet qfjk e mezua ewi oeifewy resofd, pzwm roxn ypk cxxiki oftkt fwqewi, ewi ioevfwm ypk qxc tpxokt fw ifevpewxzt rxqit. xwqa ypk mqxxn yx ypk ckty, soxxifwm xlko ypk zvvko okedpkt, skdenk nxok txnsok klkoa nfwzyk, et fr ewmkoki sa ypk evvoxedp xr ypk tzw.
```
![[Pasted image 20231031212807.png]]
```
------------------------------------------------------------------------------- CONGRATS HERE IS YOUR FLAG - FREQUENCY_IS_C_OVER_LAMBDA_OGFMAUNRAF ------------------------------------------------------------------------------- BETWEEN US THERE WAS, AS I HAVE ALREADY SAID SOMEWHERE, THE BOND OF THE SEA. BESIDES HOLDING OUR HEARTS TOGETHER THROUGH LONG PERIODS OF SEPARATION, IT HAD THE EFFECT OF MAKING US TOLERANT OF EACH OTHER'S YARNSAND EVEN CONVICTIONS. THE LAWYERTHE BEST OF OLD FELLOWSHAD, BECAUSE OF HIS MANY YEARS AND MANY VIRTUES, THE ONLY CUSHION ON DECK, AND WAS LYING ON THE ONLY RUG. THE ACCOUNTANT HAD BROUGHT OUT ALREADY A BOX OF DOMINOES, AND WAS TOYING ARCHITECTURALLY WITH THE BONES. MARLOW SAT CROSS-LEGGED RIGHT AFT, LEANING AGAINST THE MIZZEN-MAST. HE HAD SUNKEN CHEEKS, A YELLOW COMPLEXION, A STRAIGHT BACK, AN ASCETIC ASPECT, AND, WITH HIS ARMS DROPPED, THE PALMS OF HANDS OUTWARDS, RESEMBLED AN IDOL. THE DIRECTOR, SATISFIED THE ANCHOR HAD GOOD HOLD, MADE HIS WAY AFT AND SAT DOWN AMONGST US. WE EXCHANGED A FEW WORDS LAZILY. AFTERWARDS THERE WAS SILENCE ON BOARD THE YACHT. FOR SOME REASON OR OTHER WE DID NOT BEGIN THAT GAME OF DOMINOES. WE FELT MEDITATIVE, AND FIT FOR NOTHING BUT PLACID STARING. THE DAY WAS ENDING IN A SERENITY OF STILL AND EXQUISITE BRILLIANCE. THE WATER SHONE PACIFICALLY; THE SKY, WITHOUT A SPECK, WAS A BENIGN IMMENSITY OF UNSTAINED LIGHT; THE VERY MIST ON THE ESSEX MARSH WAS LIKE A GAUZY AND RADIANT FABRIC, HUNG FROM THE WOODED RISES INLAND, AND DRAPING THE LOW SHORES IN DIAPHANOUS FOLDS. ONLY THE GLOOM TO THE WEST, BROODING OVER THE UPPER REACHES, BECAME MORE SOMBRE EVERY MINUTE, AS IF ANGERED BY THE APPROACH OF THE SUN. 

|   |   |
|---|---|
|🔤₁|ESDIKRMPFBJQNWXVHOTYZLCGAU|
|🔤₂|YJWCAIXQDKEVGMRHLFBSZPNOTU|
```
## Notas adicionales
Flag: FREQUENCY_IS_C_OVER_LAMBDA_OGFMAUNRAF### waves over lambda
## Referencias

