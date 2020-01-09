---
title: Convalida della complessità delle password
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: 49e6f79c13c94a3f2f6891b259c4bb2bec54ae6f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344518"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a>Procedura dettagliata: verifica della complessità delle password (Visual Basic)
Questo metodo verifica la presenza di alcune caratteristiche di password complesse e aggiorna un parametro di stringa con informazioni sui controlli che la password ha esito negativo.  
  
 Le password possono essere utilizzate in un sistema sicuro per autorizzare un utente. Tuttavia, le password devono essere difficili da indovinare per utenti non autorizzati. Gli utenti malintenzionati possono usare un programma di *attacco del dizionario* , che scorre tutte le parole in un dizionario (o più dizionari in linguaggi diversi) e verifica se una delle parole funziona come la password di un utente. È possibile indovinare rapidamente password vulnerabili, ad esempio "Yankee" o "Mustang". Password più complesse, ad esempio "? È molto meno probabile che venga indovinato il 'L1N3vaFiNdMeyeP@sSWerd!'. Un sistema protetto da password deve garantire che gli utenti scelgano password complesse.  
  
 Una password complessa è complessa (contenente una combinazione di caratteri maiuscoli, minuscoli, numerici e speciali) e non è una parola. Questo esempio illustra come verificare la complessità.  
  
## <a name="example"></a>Esempio  
  
### <a name="code"></a>Codice  
 [!code-vb[VbVbcnRegEx#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#1)]  
  
## <a name="compile-the-code"></a>Compilare il codice  
 Chiamare questo metodo passando la stringa che contiene tale password.  
  
 L'esempio presenta i requisiti seguenti:  
  
- Accedere ai membri dello spazio dei nomi <xref:System.Text.RegularExpressions>. Aggiungere un'istruzione `Imports` se i nomi dei membri all'interno del codice non sono specificati in modo completo. Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="security"></a>Sicurezza -  
 Se si sta migrando la password in una rete, è necessario usare un metodo sicuro per il trasferimento dei dati. Per altre informazioni, vedere [sicurezza dell'applicazione Web ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).
  
 Per migliorare l'accuratezza della funzione di `ValidatePassword`, è possibile aggiungere ulteriori controlli di complessità:  
  
- Confrontare la password e le relative sottostringhe con il nome dell'utente, l'identificatore utente e un dizionario definito dall'applicazione. Inoltre, quando si eseguono i confronti, i caratteri visivi simili sono considerati equivalenti. Ad esempio, considerare le lettere "l" e "e" come equivalenti ai numeri "1" e "3".  
  
- Se è presente un solo carattere maiuscolo, assicurarsi che non sia il primo carattere della password.  
  
- Verificare che gli ultimi due caratteri della password siano caratteri letterali.  
  
- Non consentire le password in cui tutti i simboli vengono immessi dalla riga superiore della tastiera.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Text.RegularExpressions.Regex>
- [Protezione delle applicazioni Web ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))
