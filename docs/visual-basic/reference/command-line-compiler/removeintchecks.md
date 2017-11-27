---
title: /removeintchecks
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- removeintchecks
- /removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e765f0007eea8e196b1a1b3b55b969c5b074b52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="removeintchecks"></a>/removeintchecks
Attiva il controllo per le operazioni di tipo integer o disattivare l'errore di overflow.  
  
## <a name="syntax"></a>Sintassi  
  
```  
/removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`+` &#124; `-`|Parametro facoltativo. Il `/removeintchecks-` opzione indica al compilatore di verificare tutti i calcoli di integer per errori di overflow. Il valore predefinito è `/removeintchecks-`.<br /><br /> Specifica di `/removeintchecks` o `/removeintchecks+` il controllo degli errori e rendere più veloci i calcoli di integer. Tuttavia, senza errori, e se ha causato un overflow capacità di tipo di dati, senza che venga generato un errore potrebbero essere memorizzati risultati errati.|  
  
|Per impostare /removeintchecks in Visual Studio ambiente di sviluppo integrato.|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Fare clic sulla scheda **Compila**.<br />3.  Fare clic su **Avanzate** .<br />4.  Modificare il valore del **Rimuovi controllo dell'overflow di integer** casella.|  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `Test.vb` e disattiva il controllo degli errori di overflow di integer.  
  
```  
vbc /removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
