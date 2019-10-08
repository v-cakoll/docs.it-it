---
title: /debug (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- debug compiler switches
- /debug compiler option [Visual Basic]
- -debug compiler option [Visual Basic]
- debug compiler option [Visual Basic]
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
ms.openlocfilehash: c2fbe5aa6f0b9ac8c99c9b9ec5cdf0a7d9764ab8
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002400"
---
# <a name="-debug-visual-basic"></a>-debug (Visual Basic)
Consente al compilatore di generare informazioni di debug e di inserirle nei file di output.  
  
## <a name="syntax"></a>Sintassi  
  
```console 
-debug[+ | -]  
```

oppure

```console  
-debug:[full | pdbonly]  
```
  
## <a name="arguments"></a>Argomenti  
  
|Nome|Definizione|  
|---|---|  
|`+` &#124; `-`|facoltativo. Se si specifica `+` o `/debug`, il compilatore genera le informazioni di debug e le inserisce in un file con estensione pdb. La specifica di `-` ha lo stesso effetto di non specificare `/debug`.|  
|`full` &#124; `pdbonly`|facoltativo. Specifica il tipo di informazioni di debug generate dal compilatore. Se non si specifica `/debug:pdbonly`, il valore predefinito è `full`, che consente di aggiungere un debugger al programma in esecuzione. L'argomento `pdbonly` consente il debug del codice sorgente quando il programma viene avviato nel debugger, ma Visualizza il codice in linguaggio assembly solo quando il programma in esecuzione è collegato al debugger.|  
  
## <a name="remarks"></a>Note  
 Usare questa opzione per creare build di debug. Se non si specifica `/debug`, `/debug+` o `/debug:full`, non sarà possibile eseguire il debug del file di output del programma.  
  
 Per impostazione predefinita, le informazioni di debug non vengono emesse (`/debug-`). Per creare informazioni di debug, specificare `/debug` o `/debug+`.  
  
 Per informazioni su come configurare le prestazioni di debug di un'applicazione, vedere [Semplificazione del debug di un'immagine](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).  
  
|Per impostare-debug in Visual Studio Integrated Development Environment|  
|---|  
|1.  Con un progetto selezionato in **Esplora soluzioni**, scegliere **Proprietà** dal menu **Progetto**. <br />2.  Fare clic sulla scheda **Compila**.<br />3.  Fare clic su **Opzioni di compilazione avanzate**.<br />4.  Modificare il valore nella casella **genera informazioni di debug** .|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono inserite le informazioni di debug nel file di output `App.exe`.  
  
```console  
vbc -debug -out:app.exe test.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
