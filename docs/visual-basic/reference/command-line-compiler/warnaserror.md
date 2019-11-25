---
title: -warnaserror
ms.date: 03/13/2018
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
ms.openlocfilehash: f9ca5575e2a042d68fc490494f2e86991d58b80c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351714"
---
# <a name="-warnaserror-visual-basic"></a>-warnaserror (Visual Basic)
Indica al compilatore di considerare la prima occorrenza di un avviso come errore.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a>argomenti  
  
|Termine|Definizione|  
|---|---|  
|+ &#124; -|Parametro facoltativo. Per impostazione predefinita, l'opzione `-warnaserror-` è attiva. Gli avvisi non impediscono al compilatore di produrre un file di output. Con l'opzione `-warnaserror`, equivalente a `-warnaserror+`, gli avvisi vengono considerati errori.|  
|`numberList`|Parametro facoltativo. Elenco delimitato da virgole di numeri di ID di avviso a cui si applica l'opzione `-warnaserror`. Se non viene specificato alcun ID di avviso, l'opzione `-warnaserror` si applica a tutti gli avvisi.|  
  
## <a name="remarks"></a>Note  
 L'opzione `-warnaserror` considera tutti gli avvisi come errori. Qualsiasi messaggio segnalato di norma come avviso viene invece segnalato come errore. Il compilatore segnala le occorrenze successive dello stesso avviso come avvisi.  
  
 Per impostazione predefinita, l'opzione `-warnaserror-` è attiva, pertanto gli avvisi sono solo informativi. Con l'opzione `-warnaserror`, equivalente a `-warnaserror+`, gli avvisi vengono considerati errori.  
  
 Se si vuole che solo determinati avvisi vengano considerati errori, è possibile specificare un elenco delimitato da virgole di numeri di avvisi da considerare errori.  
  
> [!NOTE]
> L'opzione `-warnaserror` non controlla la modalità di visualizzazione degli avvisi. Usare l'opzione [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) per disabilitare gli avvisi.  
  
|Per impostare -warnaserror in modo da considerare tutti gli avvisi come errori nell'IDE di Visual Studio|  
|---|  
|1.  Have a project selected in **Solution Explorer**. Scegliere **Proprietà** dal menu **Progetto**. <br />2.  Click the **Compile** tab.<br />3.  Make sure the **Disable all warnings** check box is unchecked.<br />4.  Check the **Treat all warnings as errors** check box.|  
  
|Per impostare -warnaserror in modo da considerare avvisi specifici come errori nell'IDE di Visual Studio|  
|---|  
|1.  Have a project selected in **Solution Explorer**. Scegliere **Proprietà** dal menu **Progetto**.<br />2.  Click the **Compile** tab.<br />3.  Make sure the **Disable all warnings** check box is unchecked.<br />4.  Make sure the **Treat all warnings as errors** check box is unchecked.<br />5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.|  
  
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

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
