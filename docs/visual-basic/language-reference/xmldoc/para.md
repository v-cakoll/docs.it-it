---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 8f28ecc33eea99150509bb4bade047489b4b826b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352310"
---
# <a name="para-visual-basic"></a>\<para > (Visual Basic)
Specifica che il contenuto è formattato come paragrafo.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a>Parametri  
 `content`  
 Testo del paragrafo.  
  
## <a name="remarks"></a>Note  
 Il tag `<para>` è da usare all'interno di un tag, ad esempio [\<riepilogo >](../../../visual-basic/language-reference/xmldoc/summary.md), [\<osservazioni >](../../../visual-basic/language-reference/xmldoc/remarks.md)o [\<restituisce >](../../../visual-basic/language-reference/xmldoc/returns.md)e consente di aggiungere la struttura al testo.  
  
 Compilare con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene utilizzato il tag `<para>` per suddividere la sezione Osservazioni per il metodo `UpdateRecord` in due paragrafi.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
