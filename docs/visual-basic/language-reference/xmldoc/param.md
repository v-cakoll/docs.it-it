---
title: <param> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: c556b68ea99650f96ec16c220d1e2367f3e5cfde
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966489"
---
# <a name="param-visual-basic"></a>\<param> (Visual Basic)
Definisce un nome di parametro e una descrizione.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a>Parametri  
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
