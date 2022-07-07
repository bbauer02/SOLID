# Chap 4 : Liskov Substitution Principle

> **Note**
> *Lorsque vous éten­dez une classe, rap­pe­lez-vous que vous devez être en me­sure de pas­ser des ob­jets de la sous-classe à la place des ob­jets de la classe mère sans faire plan­ter le code.*

Cela sig­ni­fie que les sous-classes res­tent com­pa­tibles avec le com­por­te­ment de la classe mère. Lorsque vous re­dé­fi­nis­sez une mé­thode, éten­dez le com­por­te­ment de base plu­tôt que de le rem­pla­cer com­plè­te­ment avec autre chose.

Le **prin­cipe de subs­ti­tu­tion** est un en­semble de vé­ri­fi­ca­tions qui aide à pré­dire si une classe va res­ter com­pa­tible avec du code qui fonc­tion­nait au­pa­ra­vant avec les ob­jets de la classe mère. 

Ce con­cept est **cri­tique** lorsque vous dé­ve­lop­pez des **li­brai­ries** et des **fra­me­works** parce que vos classes vont être uti­li­sées par d’autres per­sonnes, et vous ne pour­rez pas ac­cé­der di­rec­te­ment à leur code, ni le modifier.

Con­trai­re­ment aux autres prin­cipes de con­cep­tion qui sont ou­verts à l’in­ter­pré­ta­tion, le prin­cipe de subs­ti­tu­tion im­pose des pré­re­quis aux sous-classes, et plus spé­ci­fi­que­ment à leurs mé­thodes. 

**Re­gar­dons cette liste en détail.**

* Les types des pa­ra­mètres de la mé­thode d’une sous-classe doi­vent *cor­res­pondre* ou être *plus abs­traits* que les types des pa­ra­mètres dans la mé­thode de la classe mère.

  * Pre­nons une classe avec une mé­thode qui nour­rit les chats : `feed(Cat $cat)`.
  * 

  