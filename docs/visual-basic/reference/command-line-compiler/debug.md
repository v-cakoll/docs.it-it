---
title: /debug (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- debug compiler switches
- /debug compiler option [Visual Basic]
- -debug compiler option [Visual Basic]
- debug compiler option [Visual Basic]
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
ms.openlocfilehash: 92ff9c5ea7352506c1949a77b4fb6291d63758d7
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50193799"
---
# <a name="-debug-visual-basic"></a>-debug (Visual Basic)
Indica al compilatore di generare informazioni di debug e inserirle nel file di output.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-debug[+ | -]  
' -or-  
-debug:[full | pdbonly]  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`+` &#124; `-`|Facoltativo. Che specifica `+` o `/debug` indica al compilatore di generare informazioni di debug e inserirle in un file con estensione pdb. Che specifica `-` ha lo stesso effetto se non si specifica `/debug`.|  
|`full` &#124; `pdbonly`|Facoltativo. Specifica il tipo di informazioni di debug generate dal compilatore. Se non si specifica `/debug:pdbonly`, il valore predefinito è `full`, che consente di allegare un debugger al programma in esecuzione. Il `pdbonly` argomento consente il debug di codice sorgente quando il programma viene avviato nel debugger, ma viene visualizzato codice in linguaggio assembly solo quando il programma in esecuzione è collegato al debugger.|  
  
## <a name="remarks"></a>Note  
 Usare questa opzione per creare build di debug. Se non si specifica `/debug`, `/debug+`, o `/debug:full`, non sarà possibile eseguire il debug di file di output del programma.  
  
 Per impostazione predefinita, le informazioni di debug non generate (`/debug-`). Per generare informazioni di debug, specificare `/debug` o `/debug+`.  
  
 Per informazioni su come configurare le prestazioni di debug di un'applicazione, vedere [Semplificazione del debug di un'immagine](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).  
  
|Per impostare - eseguire il debug nell'ambiente di sviluppo integrato di Visual Studio|  
|---|  
|1.  Con un progetto selezionato in **Esplora soluzioni**, scegliere **Proprietà** dal menu **Progetto**. <br />2.  Fare clic sulla scheda **Compila**.<br />3.  Fare clic su **Opzioni di compilazione avanzate**.<br />4.  Modificare il valore di **genera informazioni di Debug** casella.|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente inserisce le informazioni di debug nel file di output `App.exe`.  
  
```  
vbc -debug -out:app.exe test.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
