---
title: 'Procedura: Ricevere notifiche di eccezioni first-chance'
description: Ottenere notifiche di eccezioni first-chance in .NET tramite l'evento FirstChanceException della classe AppDomain, prima che CLR cerchi gestori di eccezioni.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- first-chance exception notifications
- exceptions, first chance notifications
ms.assetid: 66f002b8-a97d-4a6e-a503-2cec01689113
ms.openlocfilehash: e8b5ae5fb69c7befd329316aee11523f79d73fcd
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104740"
---
# <a name="how-to-receive-first-chance-exception-notifications"></a>Procedura: Ricevere notifiche di eccezioni first-chance
L'evento <xref:System.AppDomain.FirstChanceException> della classe <xref:System.AppDomain> consente di ricevere una notifica in cui si informa che è stata generata un'eccezione, prima che Common Language Runtime inizi a cercare gestori di eccezioni .

 L'evento viene generato a livello di dominio dell'applicazione. Poiché un thread di esecuzione può passare attraverso più domini dell'applicazione, un'eccezione che non viene gestita in un dominio dell'applicazione può essere gestita in un altro dominio dell'applicazione. La notifica si verifica in ogni dominio dell'applicazione che ha aggiunto un gestore per l'evento fino a quando un dominio non gestisce l'eccezione.

 Le procedure e gli esempi di questo articolo illustrano come ricevere notifiche di eccezioni first-chance in un programma semplice che include un solo dominio dell'applicazione e in un dominio dell'applicazione creato.

 Per un esempio più complesso che riguarda più domini dell'applicazione, vedere l'esempio relativo all'evento <xref:System.AppDomain.FirstChanceException>.

## <a name="receiving-first-chance-exception-notifications-in-the-default-application-domain"></a>Ricezione di notifiche di eccezioni first-chance nel dominio dell'applicazione predefinito
 Nella procedura seguente il punto di ingresso per l'applicazione, il metodo `Main()`, viene eseguito nel dominio dell'applicazione predefinito.

#### <a name="to-demonstrate-first-chance-exception-notifications-in-the-default-application-domain"></a>Per visualizzare notifiche di eccezioni first-chance nel dominio dell'applicazione predefinito

1. Definire un gestore dell'evento per l'evento <xref:System.AppDomain.FirstChanceException> usando una funzione lambda e collegarlo all'evento. In questo esempio il gestore dell'evento stampa il nome del dominio dell'applicazione in cui l'evento è stato gestito e la proprietà <xref:System.Exception.Message%2A> dell'eccezione.

     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#2)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#2)]

2. Generare un'eccezione e rilevarla. Prima che il runtime individui il gestore di eccezioni, viene generato l'evento <xref:System.AppDomain.FirstChanceException> che visualizza un messaggio. Questo messaggio è seguito dal messaggio visualizzato dal gestore di eccezioni.

     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#3)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#3)]

3. Generare un'eccezione senza rilevarla. Prima che il runtime cerchi un gestore di eccezioni, viene generato l'evento <xref:System.AppDomain.FirstChanceException> che visualizza un messaggio. Poiché non è presente alcun gestore di eccezioni, l'applicazione viene chiusa.

     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#4)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#4)]

     Il codice visualizzato nei primi tre passaggi di questa procedura forma un'applicazione console completa. L'output dell'applicazione varia a seconda del nome del file con estensione exe, perché il nome del dominio dell'applicazione predefinito è costituito dal nome e dall'estensione del file exe. Di seguito è illustrato un output di esempio.

     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#5)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#5)]

## <a name="receiving-first-chance-exception-notifications-in-another-application-domain"></a>Ricezione di notifiche di eccezioni first-chance in un altro dominio dell'applicazione
 Se il programma contiene più domini di applicazione, è possibile specificare i domini di applicazione che ricevono le notifiche.

#### <a name="to-receive-first-chance-exception-notifications-in-an-application-domain-that-you-create"></a>Per ricevere notifiche di eccezioni first-chance in un dominio dell'applicazione creato

1. Definire un gestore dell'evento per l'evento <xref:System.AppDomain.FirstChanceException>. Questo esempio usa un metodo `static` (`Shared` in Visual Basic) che stampa il nome del dominio dell'applicazione in cui l'evento viene gestito e la proprietà <xref:System.Exception.Message%2A> dell'eccezione.

     [!code-csharp[System.AppDomain.FirstChanceException_howto#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#3)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#3)]

2. Creare un dominio dell'applicazione e aggiungere il gestore dell'evento all'evento <xref:System.AppDomain.FirstChanceException> per il dominio dell'applicazione. In questo esempio il dominio dell'applicazione è denominato `AD1`.

     [!code-csharp[System.AppDomain.FirstChanceException_howto#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#2)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#2)]

     È possibile gestire questo evento nel dominio dell'applicazione predefinito nello stesso modo. Usare la proprietà `static` (`Shared` in Visual Basic) <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType> in `Main()` per ottenere un riferimento al dominio dell'applicazione predefinito.

#### <a name="to-demonstrate-first-chance-exception-notifications-in-the-application-domain"></a>Per visualizzare notifiche di eccezioni first-chance nel dominio dell'applicazione

1. Creare un oggetto `Worker` nel dominio dell'applicazione creato nella procedura precedente. La classe `Worker` deve essere pubblica e deve derivare da <xref:System.MarshalByRefObject>, come illustrato nell'esempio completo alla fine di questo articolo.

     [!code-csharp[System.AppDomain.FirstChanceException_howto#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#4)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#4)]

2. Chiamare un metodo dell'oggetto `Worker` che genera un'eccezione. In questo esempio il metodo `Thrower` viene chiamato due volte. La prima volta, poiché l'argomento del metodo è `true`, il metodo rileva la propria eccezione. La seconda volta, l'argomento è `false` e il metodo `Main()` rileva l'eccezione nel dominio dell'applicazione predefinito.

     [!code-csharp[System.AppDomain.FirstChanceException_howto#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#6)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#6)]

3. Inserire codice nel metodo `Thrower` per controllare se il metodo gestisce la propria eccezione.

     [!code-csharp[System.AppDomain.FirstChanceException_howto#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#5)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#5)]

## <a name="example"></a>Esempio
 L'esempio seguente crea un dominio dell'applicazione denominato `AD1` e aggiunge un gestore dell'evento all'evento <xref:System.AppDomain.FirstChanceException> del dominio dell'applicazione. L'esempio crea un'istanza della classe `Worker` nel dominio dell'applicazione e chiama un metodo denominato `Thrower` che genera <xref:System.ArgumentException>. A seconda del valore del proprio argomento, il metodo rileva l'eccezione o non riesce a gestirla.

 Ogni volta che il metodo `Thrower` genera un'eccezione in `AD1`, viene generato l'evento <xref:System.AppDomain.FirstChanceException> in `AD1` e il gestore dell'evento visualizza un messaggio. Il runtime cerca quindi un gestore di eccezioni. Nel primo caso il gestore di eccezioni viene trovato in `AD1`. Nel secondo caso anziché essere gestita in `AD1`, l'eccezione viene rilevata nel dominio dell'applicazione predefinito.

> [!NOTE]
> Il nome del dominio dell'applicazione predefinito è uguale al nome dell'eseguibile.

 Se si aggiunge un gestore per l'evento <xref:System.AppDomain.FirstChanceException> al dominio dell'applicazione predefinito, l'evento viene generato e gestito prima che il dominio dell'applicazione predefinito gestisca l'eccezione. Per verificarlo, aggiungere il codice C# `AppDomain.CurrentDomain.FirstChanceException += FirstChanceException;` (in Visual Basic, `AddHandler AppDomain.CurrentDomain.FirstChanceException, FirstChanceException`) all'inizio di `Main()`.

 [!code-csharp[System.AppDomain.FirstChanceException_howto#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#1)]
 [!code-vb[System.AppDomain.FirstChanceException_howto#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#1)]

## <a name="see-also"></a>Vedere anche

- <xref:System.AppDomain.FirstChanceException>
