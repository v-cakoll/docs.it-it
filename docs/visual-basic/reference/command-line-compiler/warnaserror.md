---
title: -warnaserror (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c04bff4070b0f1c288c8853e5045fbf670d8e9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655669"
---
# <a name="-warnaserror-visual-basic"></a>-warnaserror (Visual Basic)
Indica al compilatore di considerare la prima occorrenza di un avviso come errore.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|+ &#124; -|Facoltativo. Per impostazione predefinita, `-warnaserror-` è attivo; gli avvisi non impedire al compilatore che produce un file di output. Il `-warnaserror` opzione, ovvero lo stesso come `-warnaserror+`, gli avvisi vengono considerati come errori.|  
|`numberList`|Facoltativo. Elenco delimitato da virgole di ID di avviso di numeri a cui il `-warnaserror` opzione si applica. Se viene specificato alcun ID di avviso, il `-warnaserror` opzione si applica a tutti gli avvisi.|  
  
## <a name="remarks"></a>Note  
 Il `-warnaserror` opzione Considera tutti gli avvisi come errori. Tutti i messaggi che verranno in genere segnalati come avvisi vengono invece segnalati come errori. Il compilatore segnala le occorrenze successive dello stesso avviso come avvisi.  
  
 Per impostazione predefinita, `-warnaserror-` è attiva, pertanto gli avvisi solo come messaggio informativo. Il `-warnaserror` opzione, ovvero lo stesso come `-warnaserror+`, gli avvisi vengono considerati come errori.  
  
 Se si desidera che solo determinati avvisi vengano considerati errori, è possibile specificare un elenco delimitato da virgole di numeri di avvisi da considerare come errori.  
  
> [!NOTE]
>  Il `-warnaserror` opzione non controlla come vengono visualizzati gli avvisi. Usare la [- nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) opzione per disattivare gli avvisi.  
  
|Per impostare - warnaserror considerare tutti gli avvisi come errori nell'IDE di Visual Studio|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2.  Fare clic sulla scheda **Compila**.<br />3.  Verificare che il **Disabilita tutti gli avvisi** casella di controllo è deselezionata.<br />4.  Controllare il **considera tutti gli avvisi come errori** casella di controllo.|  
  
|Per impostare - warnaserror a considera avvisi specifici come errori nell'IDE di Visual Studio|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.<br />2.  Fare clic sulla scheda **Compila**.<br />3.  Verificare che il **Disabilita tutti gli avvisi** casella di controllo è deselezionata.<br />4.  Verificare che il **considera tutti gli avvisi come errori** casella di controllo è deselezionata.<br />5.  Selezionare **errore** dal **notifica** colonna adiacente all'avviso che deve essere considerato come un errore.|  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `In.vb` e indica al compilatore di visualizzare un errore per la prima occorrenza di ogni avviso generato.  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `T2.vb` e viene considerato come un errore solo l'avviso per le variabili locali inutilizzate (42024).  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
