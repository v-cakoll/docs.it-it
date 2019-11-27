---
title: <include>
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: 2f2bebfd06d4614f05cb66834cc5bef40524ce3b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348452"
---
# <a name="include-visual-basic"></a>\<includere > (Visual Basic)
Fa riferimento a un altro file che descrive i tipi e i membri nel codice sorgente.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
## <a name="parameters"></a>Parametri  
 `filename`  
 Obbligatoria. Nome del file che contiene la documentazione. È possibile qualificare il nome del file con un percorso. Racchiudere `filename` tra virgolette doppie ("").  
  
 `tagpath`  
 Obbligatoria. Percorso dei tag di `filename` che porta al `name` del tag. Racchiudere il percorso tra virgolette doppie ("").  
  
 `name`  
 Obbligatoria. Identificatore del nome nel tag che precede i commenti. `Name` avrà una `id`.  
  
 `id`  
 Obbligatoria. ID del tag che precede i commenti. Racchiudere l'ID racchiuso tra virgolette singole ('').  
  
## <a name="remarks"></a>Note  
 Usare il tag `<include>` per fare riferimento ai commenti in un altro file che descrive i tipi e i membri nel codice sorgente. eliminando la necessità di inserire i commenti relativi alla documentazione direttamente nel file del codice sorgente.  
  
 Il tag `<include>` usa la raccomandazione W3C XML Path Language (XPath) versione 1,0. Per ulteriori informazioni sulle modalità di personalizzazione dell'utilizzo `<include>`, vedere <https://www.w3.org/TR/xpath>.  
  
## <a name="example"></a>Esempio  
 Questo esempio usa il tag `<include>` per importare i commenti relativi alla documentazione dei membri da un file denominato `commentFile.xml`.  
  
 [!code-vb[VbVbcnXmlDocComments#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#4)]  
  
 Il formato del `commentFile.xml` è il seguente.  
  
```xml  
<Docs>  
<Members name="Open">  
<summary>Opens a file.</summary>  
<param name="filename">File name to open.</param>  
</Members>  
<Members name="Close">  
<summary>Closes a file.</summary>  
<param name="filename">File name to close.</param>  
</Members>  
</Docs>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
