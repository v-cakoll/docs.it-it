---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
ms.openlocfilehash: a9741f7a8283f8603e02dae5abea151c6ee5d75e
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775673"
---
# <a name="-errorreport"></a>-errorreport

Specifica il modo in cui il compilatore di Visual Basic deve segnalare gli errori interni del compilatore.

## <a name="syntax"></a>Sintassi

```console
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a>Osservazioni

Questa opzione offre un modo pratico per segnalare un errore interno del compilatore Visual Basic al team di Visual Basic di Microsoft. Per impostazione predefinita, il compilatore non invia alcuna informazione a Microsoft. Tuttavia, se si verifica un errore interno del compilatore, questa opzione consente di segnalare l'errore a Microsoft. Tali informazioni consentiranno ai tecnici Microsoft di identificare la cause e possono contribuire a migliorare la prossima versione di Visual Basic.

La capacità di un utente di inviare i report dipende dalle autorizzazioni dei criteri utente e del computer.

Nella tabella seguente sono riepilogati gli effetti dell' `-errorreport` opzione.

|Opzione|Comportamento|
|---|---|
|`prompt`|Se si verifica un errore interno del compilatore, viene visualizzata una finestra di dialogo in cui è possibile visualizzare i dati esatti raccolti dal compilatore. È possibile determinare se nel report degli errori sono presenti informazioni riservate e decidere se inviarle a Microsoft. Se si decide di inviarlo e le impostazioni dei criteri utente e del computer lo consentono, il compilatore invia i dati a Microsoft.|
|`queue`|Accoda la segnalazione errori. Quando si esegue l'accesso con privilegi di amministratore, è possibile segnalare eventuali errori dall'ultima volta che è stato effettuato l'accesso. non verrà richiesto di inviare i report per gli errori più di una volta ogni tre giorni. Si tratta del comportamento predefinito quando l' `-errorreport` opzione non è specificata.|
|`send`|Se si verifica un errore interno del compilatore e le impostazioni dei criteri utente e del computer lo consentono, il compilatore invia i dati a Microsoft.<br /><br /> L'opzione `-errorreport:send` tenta di inviare automaticamente le informazioni sugli errori a Microsoft se la creazione di report è abilitata dalle impostazioni di sistema [segnalazione errori Windows](/windows/desktop/wer/windows-error-reporting) . |
|`none`|Se si verifica un errore interno del compilatore, non verrà raccolto né inviato a Microsoft.|

Il compilatore invia i dati che includono lo stack al momento dell'errore, che in genere include un codice sorgente. Se `-errorreport` viene usato con l'opzione [-bugreport (](../../../visual-basic/reference/command-line-compiler/bugreport.md) , viene inviato l'intero file di origine.

Questa opzione è ideale per l'uso con l'opzione [-bugreport (](../../../visual-basic/reference/command-line-compiler/bugreport.md) , perché consente ai tecnici Microsoft di riprodurre più facilmente l'errore.

> [!NOTE]
> L' `-errorreport` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.

## <a name="example"></a>Esempio

Il codice seguente tenta di compilare `T2.vb`e se il compilatore rileva un errore interno del compilatore, viene richiesto di inviare la segnalazione di errore a Microsoft.

```console
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a>Vedi anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
