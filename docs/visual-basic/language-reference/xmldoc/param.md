---
title: <param> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 4bcfe96361de9e196cb684ac4ba734f82442e25c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825560"
---
# <a name="param-visual-basic"></a>\<param> (Visual Basic)
Definisce un nome di parametro e una descrizione.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a>Parametri  
 `name`  
 Nome di un parametro di metodo. Racchiudere il nome tra virgolette doppie (" ").  
  
 `description`  
 Descrizione del parametro.  
  
## <a name="remarks"></a>Note  
 Il `<param>` tag deve essere usato nel commento per una dichiarazione di metodo per descrivere uno dei parametri del metodo.  
  
 Il testo per il `<param>` tag verrà visualizzato nelle posizioni seguenti:  
  
-   Informazioni sul parametro di IntelliSense. Per altre informazioni, vedere [Using IntelliSense](/visualstudio/ide/using-intellisense) (Uso di IntelliSense).  
  
-   Visualizzatore oggetti. Per altre informazioni, vedere [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code) (Visualizzazione della struttura del codice).  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la `<param>` tag per descrivere il `id` parametro.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
