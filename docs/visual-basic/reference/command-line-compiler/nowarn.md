---
title: /nowarn
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d1eafe8d7ccd6f2c71b754dadc343518948e7146
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="nowarn"></a>/nowarn
Inibisce la capacità del compilatore di generare avvisi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
/nowarn[:numberList]  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`numberList`|Facoltativo. Elenco delimitato da virgole dei numeri di ID di avviso che il compilatore deve eliminare. Se non viene specificato l'ID di avviso, tutti gli avvisi vengono soppressi.|  
  
## <a name="remarks"></a>Note  
 Il `/nowarn` opzione, il compilatore di non generare avvisi. Per eliminare un singolo avviso, specificare l'ID di avviso per il `/nowarn` opzione dopo la virgola. Separare più numeri di avviso con virgole.  
  
 È necessario specificare solo la parte numerica dell'identificatore di avviso. Ad esempio, se si desidera eliminare BC42024, l'avviso per le variabili locali inutilizzate, specificare `/nowarn:42024`.  
  
 Per ulteriori informazioni sui numeri di ID avviso, vedere [configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
|Per impostare /nowarn in Visual Studio ambiente di sviluppo integrato.|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2.  Fare clic sulla scheda **Compila**.<br />3.  Selezionare il **Disabilita tutti gli avvisi** casella di controllo per disabilitare tutti gli avvisi.<br />     -oppure-<br />     Per disabilitare un avviso specifico, fare clic su **Nessuno** dall'elenco a discesa adiacente all'avviso.|  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `T2.vb` e non vengono visualizzati tutti gli avvisi.  
  
```  
vbc /nowarn t2.vb  
```  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `T2.vb` e non vengono visualizzati gli avvisi per le variabili locali inutilizzate (42024).  
  
```  
vbc /nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
