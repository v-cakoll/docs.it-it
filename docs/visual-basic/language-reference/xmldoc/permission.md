---
title: '&lt;autorizzazione&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 67e11998e43a43f92c26eb5f7daa488d288823c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltpermissiongt-visual-basic"></a>&lt;autorizzazione&gt; (Visual Basic)
Specifica un'autorizzazione necessaria per il membro.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a>Parametri  
 `member`  
 Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente. Il compilatore verifica l'esistenza dell'elemento di codice specificato e converte `member` nel nome canonico dell'elemento nel file XML di output. Racchiudere `member` tra virgolette ("").  
  
 `description`  
 Descrizione dell'accesso al membro.  
  
## <a name="remarks"></a>Note  
 Utilizzare il `<permission>` tag per documentare l'accesso di un membro. Utilizzare la <xref:System.Security.PermissionSet> classe per specificare l'accesso a un membro.  
  
 Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il `<permission>` tag per descrivere il <xref:System.Security.Permissions.FileIOPermission> richiesto dal `ReadFile` metodo.  
  
 [!code-vb[VbVbcnXmlDocComments#7](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/permission_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
