---
title: /imports (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e8e9cd761263b3b61a4e6d3e33c5f7f875be7a1d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imports-visual-basic"></a>/imports (Visual Basic)
Importa gli spazi dei nomi da un assembly specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
/imports:namespaceList  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`namespaceList`|Obbligatorio. Elenco delimitato da virgole degli spazi dei nomi da importare.|  
  
## <a name="remarks"></a>Note  
 Il `/imports` opzione consente di importare qualsiasi spazio dei nomi definito all'interno del gruppo di file di origine o da qualsiasi assembly di riferimento correnti.  
  
 I membri di uno spazio dei nomi specificati con `/imports` sono disponibili a tutti i file di codice sorgente nella compilazione. Utilizzare il [istruzione Imports (tipo e Namespace .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) per utilizzare uno spazio dei nomi in un file di codice sorgente singolo.  
  
|Per impostare /Imports nell'ambiente di sviluppo integrato di Visual Studio|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Fare clic sulla scheda **Riferimenti**.<br />3.  Immettere il nome dello spazio dei nomi nella casella accanto il **Aggiungi importazione utente** pulsante.<br />4.  Fare clic su di **Aggiungi importazione utente** pulsante.|  
  
## <a name="example"></a>Esempio  
 Il codice seguente viene compilato quando `/imports:system` è specificato.  
  
 [!code-vb[VbVbalrCompiler#21](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/imports_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Riferimenti e istruzione Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
