---
title: '&lt;autorizzazione&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: bcec5d968f5d0c5400c28e772df151b164888a47
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2018
ms.locfileid: "46323298"
---
# <a name="ltpermissiongt-visual-basic"></a>&lt;autorizzazione&gt; (Visual Basic)
Specifica un'autorizzazione necessaria per il membro.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a>Parametri  
 `member`  
 Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente. Il compilatore verifica l'esistenza dell'elemento di codice specificato e converte `member` nel nome canonico dell'elemento nel file XML di output. Racchiudere `member` racchiuso tra virgolette ("").  
  
 `description`  
 Descrizione dell'accesso al membro.  
  
## <a name="remarks"></a>Note  
 Usare il `<permission>` tag per documentare l'accesso di un membro. Usare il <xref:System.Security.PermissionSet> classe per specificare l'accesso a un membro.  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la `<permission>` tag per descrivere che il <xref:System.Security.Permissions.FileIOPermission> richiesto dal `ReadFile` (metodo).  
  
 [!code-vb[VbVbcnXmlDocComments#7](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/permission_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/index.md)
