---
title: La convalida della complessità delle password (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: 7bb0e3ff0d021e9923f2e1bd8ced882c6a263d15
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2019
ms.locfileid: "55738565"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a>Procedura dettagliata: Verifica della complesse delle password (Visual Basic)
Questo metodo verifica la presenza di alcune caratteristiche di password complesse e aggiorna un parametro di stringa con le informazioni sui controlli che la password ha esito negativo.  
  
 Le password è utilizzabile in un sistema sicuro per autorizzare un utente. Tuttavia, le password devono essere difficile per gli utenti non autorizzati di indovinare. Gli utenti malintenzionati possono usare una *attacco con dizionario* programma che esegue l'iterazione attraverso tutte le parole in un dizionario (o più dizionari in diverse lingue) e verifica se una delle parole funziona come una password dell'utente. Password vulnerabili, ad esempio "Yankees" o "Mustang" può essere individuata rapidamente. Password più complesse, ad esempio "? Si 'L1N3vaFiNdMeyeP@sSWerd! ", sono molto meno probabile che essere scoperti. Un sistema protetto da password è necessario assicurarsi che gli utenti scelgano le password complesse.  
  
 Una password complessa è complessa (contenente una combinazione di caratteri maiuscoli, minuscoli, numerici e speciali) e non è una parola. In questo esempio viene illustrato come verificare la complessità.  
  
## <a name="example"></a>Esempio  
  
### <a name="code"></a>Codice  
 [!code-vb[VbVbcnRegEx#1](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Chiamare questo metodo passando la stringa che contiene la password.  
  
 L'esempio presenta i requisiti seguenti:  
  
-   Accedere ai membri dello spazio dei nomi <xref:System.Text.RegularExpressions>. Aggiungere un'istruzione `Imports` se i nomi dei membri all'interno del codice non sono specificati in modo completo. Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="security"></a>Sicurezza  
 Se stai spostando la password attraverso una rete, è necessario usare un metodo sicuro per il trasferimento dei dati. Per altre informazioni, vedere [ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).
  
 È possibile migliorare l'accuratezza del `ValidatePassword` funzione mediante l'aggiunta di controlli di complessità aggiuntiva:  
  
-   Confronta le sottostringhe da un dizionario definito dall'applicazione, identificatore utente e il nome dell'utente e la password. Considerare inoltre visivamente simili caratteri come equivalenti quando si esegue il confronto. Ad esempio, considerare le lettere "l" e "e" come equivalenti ai numeri "1" e "3".  
  
-   Se è presente un solo carattere maiuscolo, assicurarsi che non è primo carattere della password.  
  
-   Assicurarsi che gli ultimi due caratteri della password sono caratteri letterali.  
  
-   Non consentire password in cui vengono immessi tutti i simboli dalla prima riga della tastiera.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Text.RegularExpressions.Regex>
- [Protezione delle applicazioni Web ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))
