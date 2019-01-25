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
ms.openlocfilehash: 3ee69999b37f3cef631a1801a800c5710ad895ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600479"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a>Tag XML consigliati per i commenti relativi alla documentazione (Visual Basic)
Il compilatore Visual Basic può elaborare i commenti della documentazione nel codice in un file XML. È possibile utilizzare strumenti aggiuntivi per elaborare il file XML nella documentazione.  
  
 Commenti in formato XML sono consentiti nei costrutti di codice, ad esempio tipi e membri dei tipi. Per i tipi parziali, solo una parte del tipo può avere commenti in formato XML, anche se non esiste alcuna restrizione sui commenti relativi membri.  
  
> [!NOTE]
>  I commenti della documentazione non è possibile applicare agli spazi dei nomi. Il motivo è che uno spazio dei nomi può estendersi a diversi assembly, e non tutti gli assembly da caricare nello stesso momento.  
  
 Il compilatore elabora tutti i tag XML valido. I tag seguenti forniscono le funzionalità comunemente utilizzate nella documentazione dell'utente.  
  
||||  
|---|---|---|  
|[\<c>](../../../visual-basic/language-reference/xmldoc/c.md)|[\<code>](../../../visual-basic/language-reference/xmldoc/code.md)|[\<example>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup>|[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup>|[\<list>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[\<para>](../../../visual-basic/language-reference/xmldoc/para.md)|[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup>|[\<paramref>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup>|[\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup>|[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup>|[\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup>|[\<value>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 (<sup>1</sup> il compilatore verifica sintassi.)  
  
> [!NOTE]
>  Se si desidera che vengano visualizzati nel testo di un commento relativo alla documentazione parentesi angolari, usare `&lt;` e `&gt;`. Ad esempio, la stringa `"&lt;text in angle brackets&gt;"` verranno visualizzati come `<text in angle brackets>`.  
  
## <a name="see-also"></a>Vedere anche
- [Documentazione del codice tramite XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
- [Procedura: Creare documentazione XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
