---
title: '&lt;para&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: fa11c713a5ed5793b50865753f8bcdeaabf56e83
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44270552"
---
# <a name="ltparagt-visual-basic"></a>&lt;para&gt; (Visual Basic)
Specifica che il contenuto viene formattato come un paragrafo.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<para>content</para>  
```  
  
#### <a name="parameters"></a>Parametri  
 `content`  
 Testo del paragrafo.  
  
## <a name="remarks"></a>Note  
 Il `<para>` tag è utilizzato all'interno di un tag, ad esempio [ \<riepilogo >](../../../visual-basic/language-reference/xmldoc/summary.md), [ \<remarks >](../../../visual-basic/language-reference/xmldoc/remarks.md), o [ \<restituisce >](../../../visual-basic/language-reference/xmldoc/returns.md), e consente di aggiungere una struttura al testo.  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la `<para>` tag per suddividere la sezione Osservazioni per il `UpdateRecord` metodo in due paragrafi.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/para_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
