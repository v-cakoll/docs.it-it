---
title: /errorreport
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0abe276aaacdeb175c3af7067dffa81448450e22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="errorreport"></a>/errorreport
Specifica la modalità di segnalazione degli errori interni del compilatore [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
## <a name="syntax"></a>Sintassi  
  
```  
/errorreport:{ prompt | queue | send | none }  
```  
  
## <a name="remarks"></a>Note  
 Questa opzione offre un modo pratico per segnalare un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] interni del compilatore sugli errori per il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] al team di Microsoft. Per impostazione predefinita, il compilatore non invia alcuna informazione a Microsoft. Tuttavia, se si verifica un errore interno del compilatore, questa opzione consente di segnalare l'errore a Microsoft. Tali informazioni consentiranno tecnici Microsoft di identificare la causa e potrebbe contribuire a migliorare la versione successiva di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
 Possibilità la di inviare report dipende dalle autorizzazioni di criteri computer e utente.  
  
 Nella tabella seguente sono riepilogati gli effetti del `/errorreport` opzione.  
  
|Opzione|Comportamento|  
|---|---|  
|`prompt`|Se si verifica un errore interno del compilatore, una finestra di dialogo viene visualizzata in modo che è possibile visualizzare esattamente i dati raccolti dal compilatore. È possibile determinare se sono presenti eventuali informazioni sensibili nella segnalazione errori e decidere se inviarlo a Microsoft. Se si decide di inviarlo, e le impostazioni dei criteri computer e l'utente lo consentono, il compilatore invierà i dati a Microsoft.|  
|`queue`|Accoda la segnalazione errori. Quando si accede con privilegi di amministratore, è possibile segnalare gli eventuali errori dall'ultima volta in cui è stato effettuato (non verrà richiesto di inviare segnalazioni errori più di una volta ogni tre giorni). Si tratta del comportamento predefinito quando il `/errorreport` opzione non è specificata.|  
|`send`|Se si verifica un errore interno del compilatore e le impostazioni di criteri computer e l'utente lo consentono, il compilatore invia i dati a Microsoft.<br /><br /> L'opzione `/errorReport:send` tenta di inviare automaticamente a Microsoft informazioni di errore. Questa opzione varia a seconda del Registro di sistema. Per ulteriori informazioni sull'impostazione dei valori appropriati nel Registro di sistema, vedere [come attivare la segnalazione errori automatica in strumenti da riga di comando di Visual Studio 2008](http://go.microsoft.com/fwlink/?LinkID=184695).|  
|`none`|Se si verifica un errore interno del compilatore, non verrà essere raccolti né inviato a Microsoft.|  
  
 Il compilatore invia i dati che includono lo stack al momento dell'errore, che in genere include codice sorgente. Se `/errorreport` viene utilizzato con il [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) opzione, viene inviato l'intero file di origine.  
  
 Questa opzione risulta particolarmente utile con il [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) opzione ammette tecnici di Microsoft più facilmente riprodurre l'errore.  
  
> [!NOTE]
>  Il `/errorreport` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente si tenterà di compilare `T2.vb`, e se il compilatore rileva un errore interno del compilatore, viene richiesto di inviare una segnalazione a Microsoft.  
  
```  
vbc /errorreport:prompt t2.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
