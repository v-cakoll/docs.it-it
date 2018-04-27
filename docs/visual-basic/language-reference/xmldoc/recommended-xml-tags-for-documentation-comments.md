---
title: Tag XML consigliati per i commenti relativi alla documentazione (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7815d4c9fddc4e760c7495ef7a2509c55141e96e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a>Tag XML consigliati per i commenti relativi alla documentazione (Visual Basic)
Il compilatore Visual Basic può elaborare i commenti della documentazione nel codice in un file XML. È possibile utilizzare strumenti aggiuntivi per elaborare il file XML nella documentazione.  
  
 I commenti XML sono consentiti nei costrutti di codice, ad esempio tipi e membri dei tipi. Per i tipi parziali, solo una parte del tipo possa contenere commenti XML, anche se non esiste alcuna restrizione sui commenti sui relativi membri.  
  
> [!NOTE]
>  Impossibile applicare i commenti della documentazione per gli spazi dei nomi. Il motivo è che uno spazio dei nomi può estendersi a diversi assembly e non tutti gli assembly devono essere caricati contemporaneamente.  
  
 Il compilatore elabora qualsiasi tag che è un XML valido. I tag seguenti forniscono funzionalità comunemente utilizzate nella documentazione dell'utente.  
  
||||  
|---|---|---|  
|[\<c>](../../../visual-basic/language-reference/xmldoc/c.md)|[\<code>](../../../visual-basic/language-reference/xmldoc/code.md)|[\<example>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|[\<eccezione >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup>|[\<includere >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup>|[\<list>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[\<para>](../../../visual-basic/language-reference/xmldoc/para.md)|[\<param >](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup>|[\<paramref>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|[\<autorizzazione >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup>|[\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|[\<vedere >](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup>|[\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup>|[\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|[\<typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup>|[\<value>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 (<sup>1</sup> il compilatore verifica la sintassi.)  
  
> [!NOTE]
>  Se si desidera venga visualizzato nel testo di un commento di documentazione tra parentesi angolari, utilizzare `<` e `>`. Ad esempio, la stringa `"<text in angle brackets>"` verrà visualizzato come `<text in angle``brackets>`.  
  
## <a name="see-also"></a>Vedere anche  
 [Documentazione del codice tramite XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [Procedura: Creare documentazione XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
