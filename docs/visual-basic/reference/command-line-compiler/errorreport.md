---
title: -errorreport
ms.date: 03/10/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8c6a81d3491f4876cfbca80aa8fda6640187176
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="-errorreport"></a>-errorreport
Specifica la modalità di segnalazione errori interni del compilatore il compilatore Visual Basic.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-errorreport:{ prompt | queue | send | none }  
```  
  
## <a name="remarks"></a>Note  
 Questa opzione offre un modo pratico per segnalare un errore interno del compilatore di Visual Basic (ICE) al team di Visual Basic in Microsoft. Per impostazione predefinita, il compilatore non invia alcuna informazione a Microsoft. Tuttavia, se si verifica un errore interno del compilatore, questa opzione consente di segnalare l'errore a Microsoft. Tali informazioni consentiranno tecnici Microsoft di identificare la causa e potrebbero contribuire a migliorare la prossima versione di Visual Basic.  
  
 Possibilità la di inviare report dipende dalle autorizzazioni di criteri computer e utente.  
  
 Nella tabella seguente sono riepilogati gli effetti del `-errorreport` opzione.  
  
|Opzione|Comportamento|  
|---|---|  
|`prompt`|Se si verifica un errore interno del compilatore, una finestra di dialogo viene visualizzata in modo che è possibile visualizzare esattamente i dati raccolti dal compilatore. È possibile determinare se sono presenti eventuali informazioni sensibili nella segnalazione errori e decidere se inviarlo a Microsoft. Se si decide di inviarlo, e le impostazioni dei criteri computer e l'utente lo consentono, il compilatore invierà i dati a Microsoft.|  
|`queue`|Accoda la segnalazione errori. Quando si accede con privilegi di amministratore, è possibile segnalare gli eventuali errori dall'ultima volta in cui è stato effettuato (non verrà richiesto di inviare segnalazioni errori più di una volta ogni tre giorni). Si tratta del comportamento predefinito quando il `-errorreport` opzione non è specificata.|  
|`send`|Se si verifica un errore interno del compilatore e le impostazioni di criteri computer e l'utente lo consentono, il compilatore invia i dati a Microsoft.<br /><br /> L'opzione `-errorreport:send` tenta di inviare automaticamente a Microsoft informazioni di errore. Questa opzione varia a seconda del Registro di sistema. Per ulteriori informazioni sull'impostazione dei valori appropriati nel Registro di sistema, vedere [come attivare la segnalazione errori automatica in strumenti da riga di comando di Visual Studio 2008](http://go.microsoft.com/fwlink/?LinkID=184695).|  
|`none`|Se si verifica un errore interno del compilatore, non verrà essere raccolti né inviato a Microsoft.|  
  
 Il compilatore invia i dati che includono lo stack al momento dell'errore, che in genere include codice sorgente. Se `-errorreport` viene usato con il [- bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) opzione, quindi viene inviato l'intero file di origine.  
  
 Questa opzione risulta particolarmente utile con il [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) opzione ammette tecnici di Microsoft più facilmente riprodurre l'errore.  
  
> [!NOTE]
>  Il `-errorreport` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente si tenterà di compilare `T2.vb`, e se il compilatore rileva un errore interno del compilatore, viene richiesto di inviare una segnalazione a Microsoft.  
  
```  
vbc -errorreport:prompt t2.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
