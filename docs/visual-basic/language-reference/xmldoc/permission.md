---
title: <permission>
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: b3acec04060367a0b9e54b19c0106644d028357b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400034"
---
# <a name="permission-visual-basic"></a>\<permission> (Visual Basic)
Specifica un'autorizzazione necessaria per il membro.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a>Parametri  
 `member`  
 Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente. Il compilatore verifica l'esistenza dell'elemento di codice specificato e converte `member` nel nome canonico dell'elemento nel file XML di output. Racchiude `member` tra virgolette ("").  
  
 `description`  
 Descrizione dell'accesso al membro.  
  
## <a name="remarks"></a>Commenti  
 Usare il `<permission>` tag per documentare l'accesso di un membro. Utilizzare la <xref:System.Security.PermissionSet> classe per specificare l'accesso a un membro.  
  
 Compilare con [-doc](../../reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio usa il `<permission>` tag per descrivere che <xref:System.Security.Permissions.FileIOPermission> è richiesto dal `ReadFile` metodo.  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a>Vedere anche

- [Tag di commento XML](index.md)
