---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 880fdf4931dadea547d64d0506bd3e978956468e
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005393"
---
# <a name="-nowarn"></a>-nowarn
Inibisce la capacità del compilatore di generare avvisi.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`numberList`|Facoltativo. Elenco delimitato da virgole dei numeri di ID avviso che il compilatore deve escludere. Se gli ID avviso non vengono specificati, vengono eliminati tutti gli avvisi.|  
  
## <a name="remarks"></a>Osservazioni  
 L' `-nowarn` opzione fa sì che il compilatore non generi avvisi. Per escludere un singolo avviso, fornire l'ID avviso all' `-nowarn` opzione che segue i due punti. Separare più numeri di avviso con virgole.  
  
 È necessario specificare solo la parte numerica dell'identificatore di avviso. Se ad esempio si desidera disattivare BC42024, viene visualizzato l'avviso relativo alle variabili locali non utilizzate `-nowarn:42024`.  
  
 Per ulteriori informazioni sui numeri ID avviso, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
|Per impostare-nowarn in Visual Studio Integrated Development Environment|  
|---|  
|1. è stato selezionato un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2. fare clic sulla scheda **Compila** .<br />3. Selezionare la casella di controllo **Disabilita tutti gli avvisi** per disabilitare tutti gli avvisi.<br />     - oppure -<br />     Per disabilitare un avviso particolare, fare clic su **nessuno** nell'elenco a discesa accanto all'avviso.|  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `T2.vb` e non visualizza alcun avviso.  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `T2.vb` e non Visualizza gli avvisi per le variabili locali non usate (42024).  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a>Vedi anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
