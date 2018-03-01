---
title: "Convalida della complessità delle password (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bdbe5f385c6b7a0898c4907b0d8afabdaed06fa0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a>Procedura dettagliata: verifica della complessità delle password (Visual Basic)
Questo metodo verifica la presenza di alcune caratteristiche di password complesse e aggiorna un parametro di stringa con informazioni sui controlli che la password non riesce.  
  
 Password può essere utilizzata in un sistema sicuro per autorizzare un utente. Tuttavia, le password devono essere difficile per gli utenti non autorizzati di indovinare. Gli utenti malintenzionati possono utilizzare un *attacco con dizionario* programma che scorre tutte le parole in un dizionario (o più dizionari in lingue diverse) e verifica se una delle parole funziona come una password. Password vulnerabili, ad esempio "Yankees" o "Mustang sono facili" può essere individuata rapidamente. Password complesse, ad esempio "? È 'L1N3vaFiNdMeyeP@sSWerd! ", sono molto meno probabile che essere individuata. Un sistema protetto da password è necessario assicurarsi che gli utenti scelgono di password complesse.  
  
 Una password complessa è complessa (contenente una combinazione di caratteri maiuscoli, minuscoli, numerici e speciali) e non è una parola. In questo esempio viene illustrato come verificare la complessità.  
  
## <a name="example"></a>Esempio  
  
### <a name="code"></a>Codice  
 [!code-vb[VbVbcnRegEx#1](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Chiamare questo metodo passando la stringa che contiene la password.  
  
 L'esempio presenta i requisiti seguenti:  
  
-   Accedere ai membri dello spazio dei nomi <xref:System.Text.RegularExpressions>. Aggiungere un'istruzione `Imports` se i nomi dei membri all'interno del codice non sono specificati in modo completo. Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="security"></a>Sicurezza  
 Se si sta spostando la password attraverso una rete, è necessario utilizzare un metodo sicuro per il trasferimento dei dati. Per ulteriori informazioni, vedere [sicurezza delle applicazioni Web ASP.NET](https://msdn.microsoft.com/library/330a99hc).  
  
 È possibile migliorare l'accuratezza del `ValidatePassword` funzione tramite l'aggiunta di controlli di complessità aggiuntive:  
  
-   Confrontare la password e le sue sottostringhe con il nome dell'utente, l'ID utente e un dizionario definito dall'applicazione. Inoltre, gestiscono visivamente simili caratteri come equivalenti quando si esegue il confronto. Ad esempio, considerare le lettere "l" e "e" come equivalenti ai numeri "1" e "3".  
  
-   Se è presente un solo carattere maiuscolo, assicurarsi che non è primo carattere della password.  
  
-   Assicurarsi che gli ultimi due caratteri della password sono caratteri lettera.  
  
-   Non consentire password nel quale sono inseriti tutti i simboli dalla prima riga della tastiera.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Text.RegularExpressions.Regex>  
 [Protezione delle applicazioni Web ASP.NET](https://msdn.microsoft.com/library/330a99hc)
