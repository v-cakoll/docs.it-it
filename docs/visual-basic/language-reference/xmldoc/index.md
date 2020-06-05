---
title: Tag XML consigliati per i commenti relativi alla documentazione
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: af57fc7d55c5cfda24a2fd9406b17dedee898760
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400099"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a>Tag XML consigliati per i commenti relativi alla documentazione (Visual Basic)
Il compilatore Visual Basic può elaborare i commenti della documentazione nel codice in un file XML. È possibile utilizzare altri strumenti per elaborare il file XML nella documentazione di.  
  
 I commenti XML sono consentiti in costrutti di codice, ad esempio tipi e membri di tipo. Per i tipi parziali, solo una parte del tipo può presentare commenti XML, anche se non esiste alcuna restrizione per il commento dei relativi membri.  
  
> [!NOTE]
> Non è possibile applicare i commenti alla documentazione agli spazi dei nomi. Il motivo è che uno spazio dei nomi può estendersi su più assembly e non tutti gli assembly devono essere caricati contemporaneamente.  
  
 Il compilatore elabora qualsiasi tag che è un XML valido. I seguenti tag forniscono la funzionalità comunemente utilizzata nella documentazione dell'utente.  
  
||||  
|---|---|---|  
|[\<c>](c.md)|[\<code>](code.md)|[\<example>](example.md)|  
|[\<exception>](exception.md)<sup>1</sup>|[\<include>](include.md)<sup>1</sup>|[\<list>](list.md)|  
|[\<para>](para.md)|[\<param>](param.md)<sup>1</sup>|[\<paramref>](paramref.md)|  
|[\<permission>](permission.md)<sup>1</sup>|[\<remarks>](remarks.md)|[\<returns>](returns.md)|  
|[\<see>](see.md)<sup>1</sup>|[\<seealso>](seealso.md)<sup>1</sup>|[\<summary>](summary.md)|  
|[\<typeparam>](typeparam.md)<sup>1</sup>|[\<value>](value.md)||  
  
 (<sup>1</sup> il compilatore verifica la sintassi).  
  
> [!NOTE]
> Se si desidera che le parentesi angolari vengano visualizzate nel testo di un commento della documentazione, utilizzare `&lt;` e `&gt;` . Ad esempio, la stringa `"&lt;text in angle brackets&gt;"` viene visualizzata come `<text in angle brackets>` .  
  
## <a name="see-also"></a>Vedere anche

- [Documentazione del codice tramite XML](../../programming-guide/program-structure/documenting-your-code-with-xml.md)
- [-doc](../../reference/command-line-compiler/doc.md)
- [Procedura: Creare documentazione XML](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
