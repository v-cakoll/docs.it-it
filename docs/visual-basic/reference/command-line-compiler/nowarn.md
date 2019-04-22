---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 31f7a2b771cfa1bcc6581d720aa0de3505aec826
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58828212"
---
# <a name="-nowarn"></a>-nowarn
Inibisce la capacità del compilatore di generare avvisi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`numberList`|Facoltativo. Elenco delimitato da virgole dei numeri di ID di avviso che il compilatore deve eliminare. Se non viene specificato gli ID avviso, vengono eliminati tutti gli avvisi.|  
  
## <a name="remarks"></a>Note  
 Il `-nowarn` opzione indica al compilatore di non generare avvisi. Per eliminare un singolo avviso, specificare l'ID di avviso per il `-nowarn` opzione che segue i due punti. Separare più numeri di avviso con virgole.  
  
 È necessario specificare solo la parte numerica dell'identificatore di avviso. Ad esempio, se si desidera eliminare BC42024, l'avviso per le variabili locali inutilizzate, specificare `-nowarn:42024`.  
  
 Per altre informazioni sui numeri di ID di avviso, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
|Per impostare - nowarn nell'ambiente di sviluppo integrato di Visual Studio|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2.  Fare clic sulla scheda **Compila**.<br />3.  Selezionare il **Disabilita tutti gli avvisi** casella di controllo per disabilitare tutti gli avvisi.<br />     -oppure-<br />     Per disabilitare un avviso specifico, fare clic su **None** dall'elenco a discesa adiacente all'avviso.|  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `T2.vb` e non vengono visualizzati tutti gli avvisi.  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `T2.vb` e non vengono visualizzati gli avvisi per le variabili locali inutilizzate (42024).  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
