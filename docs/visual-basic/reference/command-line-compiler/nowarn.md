---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 37851f99eb88543e939ce48995ded41958e57cc3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397488"
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
|`numberList`|Facoltativa. Elenco delimitato da virgole dei numeri di ID avviso che il compilatore deve escludere. Se gli ID avviso non vengono specificati, vengono eliminati tutti gli avvisi.|  
  
## <a name="remarks"></a>Commenti  
 L' `-nowarn` opzione fa sì che il compilatore non generi avvisi. Per escludere un singolo avviso, fornire l'ID avviso all' `-nowarn` opzione che segue i due punti. Separare più numeri di avviso con virgole.  
  
 È necessario specificare solo la parte numerica dell'identificatore di avviso. Se ad esempio si desidera disattivare BC42024, viene visualizzato l'avviso relativo alle variabili locali non utilizzate `-nowarn:42024` .  
  
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
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
- [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
