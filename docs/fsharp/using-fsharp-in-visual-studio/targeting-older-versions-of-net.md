---
title: Impostazione di .NET Framework 2.0 come destinazione in Windows 8
description: 'Informazioni sulla scelta di una versione precedente di .NET Framework quando si usa F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 9b08cced63b46778a5081d4de710991a6299fd29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566970"
---
# <a name="targeting-older-versions-of-net"></a>Definizione di versioni precedenti di .NET come destinazione

> [!NOTE]
In questo articolo non è aggiornato con il più recente di Visual Studio.  Verrà eseguito un aggiornamento.

Potrebbe essere visualizzato l'errore seguente se si tenta di destinazione di .NET Framework 2.0, 3.0 o 3.5 in F # del progetto quando Visual Studio è installato in Windows 8.1: 

```
This project requires the 2.0 F# runtime, but that runtime is not installed.
```

Questo errore è noto che si verifichi nella combinazione delle condizioni seguente:


- Visual Studio è installato in Windows 8.1.
<br />

- È stato abilitato .NET Framework 3.5 prima di installare Visual Studio.
<br />

- Il progetto è destinato a .NET Framework 2.0, 3.0 o 3.5.
<br />

Quando si installa Visual Studio, rileva le versioni installate di .NET Framework e installa il Runtime 2.0 F # solo se .NET Framework 3.5 è installato e abilitato.


## <a name="resolving-the-error"></a>Risolvere l'errore
Per correggere l'errore, è possibile destinazione una versione più recente di .NET Framework oppure è possibile abilitare .NET Framework 3.5 in Windows 8.1 e quindi installare il runtime di F # 2.0 eseguendo il programma di installazione per Visual Studio con il **ripristino** opzione.


#### <a name="to-enable-the-net-framework-35-on-windows-81"></a>Per abilitare .NET Framework 3.5 in Windows 8.1

1. Nel **avviare** schermata, iniziare a immettere **Pannello di controllo**.
<br />  Quando si immette il nome, il **Pannello di controllo** icona viene visualizzata sotto il **app** intestazione.
<br />

2. Scegliere il **Pannello di controllo** icona, scegliere il **programmi** icona e quindi scegliere il **o disattivazione delle funzionalità Windows attivare** collegamento.
<br />

3. Assicurarsi che il **.NET Framework 3.5 (include .NET 2.0 e 3.0)** casella di controllo è selezionata e quindi scegliere il **OK** pulsante.
<br />  Non è necessario selezionare le caselle di controllo per tutti i nodi figlio dei componenti facoltativi di .NET Framework.
<br />  .NET Framework 3.5 è abilitata se non è stato già.
<br />


#### <a name="to-install-the-f-20-runtime"></a>Per installare il runtime di F # 2.0

1. Nel Pannello di controllo, scegliere il **programmi** collegamento e quindi scegliere il **programmi e funzionalità** collegamento.
<br />

2. Nell'elenco dei programmi installati, selezionare l'edizione di Visual Studio è installato e quindi scegliere il **modifica** pulsante.
<br />

3. Dopo l'avvio dell'installazione, scegliere il **ripristino** pulsante.
<br />  Per ulteriori informazioni, vedere [installazione di Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx).
<br />
## <a name="see-also"></a>Vedere anche
[Visual F#](../index.md)
