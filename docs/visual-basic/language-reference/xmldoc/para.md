---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 0e2051d1b00b881c06082b3af483890d8595899f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400073"
---
# <a name="para-visual-basic"></a>\<para> (Visual Basic)
Specifica che il contenuto è formattato come paragrafo.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a>Parametri  
 `content`  
 Testo del paragrafo.  
  
## <a name="remarks"></a>Commenti  
 Il `<para>` tag è da usare all'interno di un tag, ad esempio [\<summary>](summary.md) , [\<remarks>](remarks.md) o [\<returns>](returns.md) , e consente di aggiungere la struttura al testo.  
  
 Compilare con [-doc](../../reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio usa il `<para>` tag per suddividere la sezione Osservazioni per il `UpdateRecord` metodo in due paragrafi.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Tag di commento XML](index.md)
