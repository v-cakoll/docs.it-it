---
title: Tag XML consigliati per i commenti relativi alla documentazione (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: 2d6519af8ca1a0e2d59131eec4d63646dce7318b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913509"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a>Tag XML consigliati per i commenti relativi alla documentazione (Visual Basic)
Il compilatore Visual Basic può elaborare i commenti della documentazione nel codice in un file XML. È possibile utilizzare altri strumenti per elaborare il file XML nella documentazione di.  
  
 I commenti XML sono consentiti in costrutti di codice, ad esempio tipi e membri di tipo. Per i tipi parziali, solo una parte del tipo può presentare commenti XML, anche se non esiste alcuna restrizione per il commento dei relativi membri.  
  
> [!NOTE]
> Non è possibile applicare i commenti alla documentazione agli spazi dei nomi. Il motivo è che uno spazio dei nomi può estendersi su più assembly e non tutti gli assembly devono essere caricati contemporaneamente.  
  
 Il compilatore elabora qualsiasi tag che è un XML valido. I seguenti tag forniscono la funzionalità comunemente utilizzata nella documentazione dell'utente.  
  
||||  
|---|---|---|  
|[\<c>](../../../visual-basic/language-reference/xmldoc/c.md)|[\<code>](../../../visual-basic/language-reference/xmldoc/code.md)|[\<example>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup>|[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup>|[\<list>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[\<para>](../../../visual-basic/language-reference/xmldoc/para.md)|[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup>|[\<paramref>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup>|[\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup>|seealso > <sup>1</sup> [ \<](../../../visual-basic/language-reference/xmldoc/seealso.md)|[\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|typeparam > <sup>1</sup> [ \<](../../../visual-basic/language-reference/xmldoc/typeparam.md)|[\<value>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 (<sup>1</sup> il compilatore verifica la sintassi).  
  
> [!NOTE]
> Se si desidera che le parentesi angolari vengano visualizzate nel testo di un commento della `&lt;` documentazione `&gt;`, utilizzare e. Ad esempio, la stringa `"&lt;text in angle brackets&gt;"` viene visualizzata come `<text in angle brackets>`.  
  
## <a name="see-also"></a>Vedere anche

- [Documentazione del codice tramite XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
- [Procedura: Creazione della documentazione XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
