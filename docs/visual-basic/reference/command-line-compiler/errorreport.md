---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d093b8ce4413a375e79eec239be37e83ac674d05
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43417649"
---
# <a name="-errorreport"></a>-errorreport

Specifica la modalità di segnalazione errori interni del compilatore il compilatore Visual Basic.

## <a name="syntax"></a>Sintassi

```
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a>Note

Questa opzione offre un modo pratico per segnalare un errore interno del compilatore Visual Basic (ICE) al team di Visual Basic presso Microsoft. Per impostazione predefinita, il compilatore non invia alcuna informazione per Microsoft. Tuttavia, se si verifica un errore del compilatore interno, questa opzione consente di segnalare l'errore a Microsoft. Tali informazioni consentono i tecnici Microsoft di identificare la causa e potrebbero contribuire a migliorare la prossima versione di Visual Basic.

Possibilità di un utente di inviare report dipende dalle autorizzazioni di criteri utente e computer.

Nella tabella seguente sono riepilogati gli effetti del `-errorreport` opzione.

|Opzione|Comportamento|
|---|---|
|`prompt`|Se si verifica un errore interno del compilatore, una finestra di dialogo viene visualizzata in modo che è possibile visualizzare i dati esatti raccolti dal compilatore. È possibile determinare se sono presenti eventuali informazioni sensibili nella segnalazione dell'errore e prendere la decisione se si desidera inviare a Microsoft. Se si decide di inviarle e consentiranno le impostazioni dei criteri computer e utente, il compilatore invia i dati a Microsoft.|
|`queue`|Accoda la segnalazione errori. Quando si accede con privilegi di amministratore, è possibile segnalare gli eventuali errori dall'ultima volta si fosse connessi in (non verrà richiesto di inviare segnalazioni errori più di una volta ogni tre giorni). Si tratta del comportamento predefinito quando il `-errorreport` opzione non è specificata.|
|`send`|Se si verifica un errore interno del compilatore, e le impostazioni dei criteri computer e l'utente lo consentono, il compilatore invia i dati a Microsoft.<br /><br /> L'opzione `-errorreport:send` tenta di inviare automaticamente le informazioni sugli errori a Microsoft se reporting è abilitato per il [segnalazione errori Windows](/windows/desktop/wer/windows-error-reporting) le impostazioni di sistema. |
|`none`|Se si verifica un errore interno del compilatore, non verrà essere raccolti né inviato a Microsoft.|

Il compilatore invia i dati che includono lo stack al momento dell'errore, che in genere include codice sorgente. Se `-errorreport` viene usato con il [- bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) opzione, non viene inviato l'intero file di origine.

Questa opzione risulta particolarmente utile con i [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) opzione perché consente a ingegneri Microsoft più facilmente riprodurre l'errore.

> [!NOTE]
> Il `-errorreport` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.

## <a name="example"></a>Esempio

Il codice seguente tenta di compilare `T2.vb`, e se il compilatore rileva un errore interno del compilatore, viene richiesto di inviare una segnalazione a Microsoft.

```
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
