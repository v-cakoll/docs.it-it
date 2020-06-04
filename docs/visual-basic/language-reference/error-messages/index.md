---
title: messaggi di errore
ms.date: 07/20/2015
helpviewer_keywords:
- errors [Visual Basic]
- error messages
- trappable errors
- errors [Visual Basic], trappable
ms.assetid: f2dda05b-baef-41f5-8bb1-598bd7cf239f
ms.openlocfilehash: c2d9974f41efdd321af800e6270586d9b18ba6f7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402850"
---
# <a name="error-messages-visual-basic"></a>Messaggi di errore (Visual Basic)
Quando si scrive, compila o esegue un'applicazione Visual Basic, possono verificarsi i tipi di errori seguenti:  
  
1. Errori in fase di progettazione, che si verificano quando si scrive un'applicazione in Visual Studio.  
  
2. Errori in fase di compilazione, che si verificano quando si compila un'applicazione in Visual Studio o da un prompt dei comandi.  
  
3. Errori di runtime, che si verificano quando si esegue un'applicazione in Visual Studio o come file eseguibile autonomo.  
  
 Per altre informazioni sulla risoluzione di problemi specifici, vedere [Risorse aggiuntive per i programmatori Visual Basic](../../getting-started/additional-resources.md).  
  
## <a name="run-time-errors"></a>Errori di runtime  
 Se un'applicazione Visual Basic tenta di eseguire un'azione che il sistema non è in grado di eseguire, si verifica un errore di run-time e Visual Basic genera un `Exception` oggetto. Visual Basic possibile generare errori personalizzati di qualsiasi tipo di dati, inclusi `Exception` gli oggetti, utilizzando l' `Throw` istruzione. Un'applicazione può identificare l'errore visualizzando il numero e il messaggio di errore di un'eccezione rilevata. Se non viene rilevato alcun errore, l'applicazione termina.  
  
 Il codice può intercettare e analizzare errori di runtime. Se si include il codice che genera l'errore in un blocco `Try`, è possibile rilevare qualsiasi errore generato all'interno di un blocco `Catch` corrispondente. Per informazioni su come intercettare gli errori di runtime e gestirli nel codice, vedere [Istruzione Try...Catch...Finally](../statements/try-catch-finally-statement.md).  
  
## <a name="compile-time-errors"></a>Errori in fase di compilazione  
 Se il compilatore Visual Basic rileva un errore nel codice, si verifica un errore in fase di compilazione. Nell'editor di codice è possibile identificare facilmente la riga del codice che ha determinato l'errore poiché sotto tale riga viene visualizzata una sottolineatura ondulata. Per visualizzare il messaggio di errore, posizionare il mouse sulla linea ondulata o aprire **Elenco errori**, in cui sono riportati anche altri messaggi.  
  
 Se un identificatore presenta una linea ondulata e una sottolineatura breve sotto il carattere all'estrema destra, è possibile generare uno stub per la classe, il costruttore, il metodo, la proprietà, il campo o l'enumerazione. Per altre informazioni, vedere [Generazione dall'utilizzo](/visualstudio/ide/visual-csharp-intellisense#generate-from-usage).
  
 La risoluzione degli avvisi visualizzati dal compilatore Visual Basic consente di scrivere codice più veloce e con meno bug. Questi avvisi identificano il codice che può generare errori durante l'esecuzione dell'applicazione. Ad esempio, il compilatore genera un avviso quando si cerca di chiamare un membro di una variabile di oggetto non assegnata, di completare l'esecuzione di una funzione senza impostare il valore restituito o di eseguire un blocco `Try` con errori nel codice per l'intercettazione delle eccezioni. Per altre informazioni sugli avvisi, incluso il modo di attivarli e disattivarli, vedere [Configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).
