---
title: Timer
description: Informazioni su quali timer .NET usare in un ambiente con multithreading.
ms.date: 07/03/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
author: pkulikov
ms.openlocfilehash: d463eb2a8d598dc5ba9b2fb51a6fc08c563e6fe4
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739493"
---
# <a name="timers"></a>Timer

.NET fornisce due timer da usare in un ambiente con multithreading:

- <xref:System.Threading.Timer?displayProperty=nameWithType>, che esegue un metodo di callback singolo su un thread <xref:System.Threading.ThreadPool> a intervalli regolari.
- <xref:System.Timers.Timer?displayProperty=nameWithType>, che per impostazione predefinita genera un evento in un thread <xref:System.Threading.ThreadPool> a intervalli regolari.

> [!NOTE]
> Alcune implementazioni .NET possono includere altri timer:
>
> - <xref:System.Windows.Forms.Timer?displayProperty=nameWithType>: un componente di Windows Form che genera un evento a intervalli regolari. Il componente non dispone di interfacce utente ed è progettato per l'uso in un ambiente a thread singolo.  
> - <xref:System.Web.UI.Timer?displayProperty=nameWithType>: un componente ASP.NET che esegue postback asincroni o sincroni di pagina Web in base a intervalli regolari.
> - <xref:System.Windows.Threading.DispatcherTimer?displayProperty=nameWithType>: un timer integrato nella coda del <xref:System.Windows.Threading.Dispatcher> che viene elaborata in un intervallo di tempo specifico e con una priorità specifica.

## <a name="the-systemthreadingtimer-class"></a>Classe System.Threading.Timer

La classe <xref:System.Threading.Timer?displayProperty=nameWithType> consente di chiamare in modo continuativo un delegato a determinati intervalli di tempo. È inoltre possibile utilizzare questa classe per pianificare una singola chiamata a un delegato in un intervallo di tempo specificato. Il delegato viene eseguito su un thread <xref:System.Threading.ThreadPool>.

Quando si crea un oggetto <xref:System.Threading.Timer?displayProperty=nameWithType>, si specifica un delegato <xref:System.Threading.TimerCallback> che definisce il metodo di callback, un oggetto di stato facoltativo passato al callback, il tempo di attesa prima della prima chiamata di callback e l'intervallo di tempo tra le chiamate di callback. Per annullare un timer in sospeso, chiamare il metodo <xref:System.Threading.Timer.Dispose%2A?displayProperty=nameWithType>.

L'esempio seguente illustra come creare un timer che chiama il delegato fornito per la prima volta dopo un secondo (1000 millisecondi) e quindi ogni due secondi. L'oggetto di stato nell'esempio viene usato per contare quante volte viene chiamato il delegato. Il timer viene arrestato dopo aver chiamato il delegato almeno 10 volte.

[!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
[!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
[!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]

Per altre informazioni ed esempi, vedere <xref:System.Threading.Timer?displayProperty=nameWithType>.

## <a name="the-systemtimerstimer-class"></a>Classe System.Timers.Timer

Un altro timer utilizzabile in un ambiente con multithreading è <xref:System.Timers.Timer?displayProperty=nameWithType>, che per impostazione predefinita genera un evento in un thread <xref:System.Threading.ThreadPool>.

Quando si crea un oggetto <xref:System.Timers.Timer?displayProperty=nameWithType>, è possibile specificare l'intervallo di tempo in cui si desidera generare un evento <xref:System.Timers.Timer.Elapsed>. Usare la proprietà <xref:System.Timers.Timer.Enabled%2A> per indicare se un timer deve generare un evento <xref:System.Timers.Timer.Elapsed>. Se un evento <xref:System.Timers.Timer.Elapsed> deve essere generato una sola volta dopo l'intervallo specificato, impostare <xref:System.Timers.Timer.AutoReset%2A> su `false`. Il valore predefinito della proprietà <xref:System.Timers.Timer.AutoReset%2A> è `true`, vale a dire che un evento <xref:System.Timers.Timer.Elapsed> viene generato periodicamente in base all'intervallo definito dalla proprietà <xref:System.Timers.Timer.Interval%2A>.

Per altre informazioni ed esempi, vedere <xref:System.Timers.Timer?displayProperty=nameWithType>.
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Timer?displayProperty=nameWithType>
- <xref:System.Timers.Timer?displayProperty=nameWithType>
- [Funzionalità e oggetti di threading](threading-objects-and-features.md)
