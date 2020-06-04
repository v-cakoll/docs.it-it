---
title: -warnaserror
ms.date: 03/13/2018
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
ms.openlocfilehash: 94a8b43a891df9837925869e17fac4536a995264
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414272"
---
# <a name="-warnaserror-visual-basic"></a>-warnaserror (Visual Basic)
Indica al compilatore di considerare la prima occorrenza di un avviso come errore.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|+ &#124; -|Facoltativa. Per impostazione predefinita, l'opzione `-warnaserror-` è attiva. Gli avvisi non impediscono al compilatore di produrre un file di output. Con l'opzione `-warnaserror`, equivalente a `-warnaserror+`, gli avvisi vengono considerati errori.|  
|`numberList`|Facoltativa. Elenco delimitato da virgole di numeri di ID di avviso a cui si applica l'opzione `-warnaserror`. Se non viene specificato alcun ID di avviso, l'opzione `-warnaserror` si applica a tutti gli avvisi.|  
  
## <a name="remarks"></a>Commenti  
 L'opzione `-warnaserror` considera tutti gli avvisi come errori. Qualsiasi messaggio segnalato di norma come avviso viene invece segnalato come errore. Il compilatore segnala le occorrenze successive dello stesso avviso come avvisi.  
  
 Per impostazione predefinita, l'opzione `-warnaserror-` è attiva, pertanto gli avvisi sono solo informativi. Con l'opzione `-warnaserror`, equivalente a `-warnaserror+`, gli avvisi vengono considerati errori.  
  
 Se si vuole che solo determinati avvisi vengano considerati errori, è possibile specificare un elenco delimitato da virgole di numeri di avvisi da considerare errori.  
  
> [!NOTE]
> L'opzione `-warnaserror` non controlla la modalità di visualizzazione degli avvisi. Usare l'opzione [-nowarn](nowarn.md) per disabilitare gli avvisi.  
  
|Per impostare -warnaserror in modo da considerare tutti gli avvisi come errori nell'IDE di Visual Studio|  
|---|  
|1. è stato selezionato un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2. fare clic sulla scheda **Compila** .<br />3. Assicurarsi che la casella di controllo **Disabilita tutti gli avvisi** sia deselezionata.<br />4. Selezionare la casella **di controllo Considera tutti gli avvisi come errori** .|  
  
|Per impostare -warnaserror in modo da considerare avvisi specifici come errori nell'IDE di Visual Studio|  
|---|  
|1. è stato selezionato un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.<br />2. fare clic sulla scheda **Compila** .<br />3. Assicurarsi che la casella di controllo **Disabilita tutti gli avvisi** sia deselezionata.<br />4. Assicurarsi che la casella **di controllo Considera tutti gli avvisi come errori** sia deselezionata.<br />5. Selezionare **errore** nella colonna **notifica** accanto all'avviso che deve essere considerato come un errore.|  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `In.vb` e indica al compilatore di visualizzare un errore per la prima occorrenza di ogni avviso rilevato.  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `T2.vb` e considera come errore solo l'avviso per le variabili locali inutilizzate (42024).  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
- [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
