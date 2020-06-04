---
title: <include>
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: 78a10624107cea349b01f484c641190a945dbd7e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400111"
---
# <a name="include-visual-basic"></a>\<include> (Visual Basic)
Fa riferimento a un altro file che descrive i tipi e i membri nel codice sorgente.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
## <a name="parameters"></a>Parametri  
 `filename`  
 Obbligatorio. Nome del file che contiene la documentazione. È possibile qualificare il nome del file con un percorso. Racchiude `filename` tra virgolette doppie ("").  
  
 `tagpath`  
 Obbligatorio. Percorso dei tag di `filename` che porta al `name` del tag. Racchiudere il percorso tra virgolette doppie ("").  
  
 `name`  
 Obbligatorio. Identificatore del nome nel tag che precede i commenti. `Name`avrà un `id` .  
  
 `id`  
 Obbligatorio. ID del tag che precede i commenti. Racchiudere l'ID racchiuso tra virgolette singole ('').  
  
## <a name="remarks"></a>Commenti  
 Usare il `<include>` tag per fare riferimento ai commenti in un altro file che descrive i tipi e i membri nel codice sorgente. eliminando la necessità di inserire i commenti relativi alla documentazione direttamente nel file del codice sorgente.  
  
 Il `<include>` tag usa la raccomandazione W3C XML Path Language (XPath) versione 1,0. Per ulteriori informazioni sulle modalità di personalizzazione dell' `<include>` utilizzo, vedere <https://www.w3.org/TR/xpath> .  
  
## <a name="example"></a>Esempio  
 Questo esempio usa il `<include>` tag per importare i commenti relativi alla documentazione membri da un file denominato `commentFile.xml` .  
  
 [!code-vb[VbVbcnXmlDocComments#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#4)]  
  
 Il formato di `commentFile.xml` è il seguente.  
  
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

- [Tag di commento XML](index.md)
