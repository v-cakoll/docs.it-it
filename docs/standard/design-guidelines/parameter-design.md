---
title: Progettazione di parametri
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
author: KrzysztofCwalina
ms.openlocfilehash: 5a0f6e0fab5d0f2fe8574e348fc6b8ae726eeb99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757404"
---
# <a name="parameter-design"></a>Progettazione di parametri
Questa sezione vengono fornite linee guida generali sulla progettazione di parametro, incluse le sezioni con le linee guida per la verifica di argomenti. Inoltre, è consigliabile consultare le linee guida descritte nel [parametri di denominazione](../../../docs/standard/design-guidelines/naming-parameters.md).  
  
 **✓ DO** utilizzare il tipo di parametro meno derivato che fornisce le funzionalità richieste da un membro.  
  
 Si supponga, ad esempio, che si vuole progettare un metodo che enumera una raccolta e la stampa di ogni elemento nella console. Tale metodo richiederà <xref:System.Collections.IEnumerable> come parametro, non <xref:System.Collections.ArrayList> o <xref:System.Collections.IList>, ad esempio.  
  
 **X DO NOT** utilizzare parametri riservati.  
  
 Se sono necessarie più input per un membro nelle versioni future, è possibile aggiungere un nuovo overload.  
  
 **X DO NOT** sono esposte pubblicamente i metodi che accettano puntatori, matrici di puntatori o le matrici multidimensionali come parametri.  
  
 I puntatori e matrici multidimensionali sono relativamente difficili da utilizzare in modo appropriato. Nella quasi totalità dei casi, le API possono essere riprogettate per evitare di creare questi tipi come parametri.  
  
 **✓ DO** inserire tutti `out` parametri che seguono tutti il base al valore e `ref` parametri (esclusi matrici di parametro), anche se il risultato è un'incoerenza nel parametro ordinamento viene eseguito tra gli overload (vedere [membro L'overload](../../../docs/standard/design-guidelines/member-overloading.md)).  
  
 Il `out` parametri possono essere considerati come valori di ritorno a capo e raggruppandoli rende la firma del metodo più facile da comprendere.  
  
 **✓ DO** sia sempre coerente denominazione dei parametri quando si esegue l'override di membri o di implementazione di membri di interfaccia.  
  
 Ciò comunica meglio la relazione tra i metodi.  
  
### <a name="choosing-between-enum-and-boolean-parameters"></a>Scelta tra l'enumerazione e i parametri booleani  
 **✓ DO** utilizzare enumerazioni se un membro in caso contrario sarebbe due o più parametri booleani.  
  
 **X DO NOT** utilizzare valori booleani, a meno che non si è assolutamente certi non sarà mai necessario per più di due valori.  
  
 Le enumerazioni offrono un margine di future addizione dei valori, ma è necessario essere consapevoli di tutte le implicazioni dell'aggiunta di valori alle enumerazioni senza ambito, descritte nelle [progettazione di Enum](../../../docs/standard/design-guidelines/enum.md).  
  
 **✓ CONSIDER** utilizzando valori booleani per i parametri del costruttore che sono realmente due stati, valori e vengono utilizzati per inizializzare le proprietà booleane.  
  
### <a name="validating-arguments"></a>Convalida di argomenti  
 **✓ DO** convalidare gli argomenti passati ai membri pubblici, protetti o implementati in modo esplicito. Generare <xref:System.ArgumentException?displayProperty=nameWithType>, o una delle sue sottoclassi, se la convalida non riesce.  
  
 Si noti che la convalida effettiva non deve necessariamente essere eseguita nel membro pubblico o protetto se stesso. Questo può verificarsi a un livello inferiore in alcune routine privato o interno. Il punto principale è che l'intera area di superficie esposta agli utenti finali controlla gli argomenti.  
  
 **✓ DO** throw <xref:System.ArgumentNullException> se viene passato un argomento null e il membro non supporta argomenti null.  
  
 **✓ DO** convalidare i parametri enum.  
  
 Non presupporre enum argomenti sarà compreso nell'intervallo definito dal tipo enum. CLR consente di eseguire il cast di qualsiasi valore intero in un valore enum, anche se il valore non è definito nell'enumerazione.  
  
 **X DO NOT** utilizzare <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> per intervallo di enumerazione controlla.  
  
 **✓ DO** tenere presente che gli argomenti modificabili sia stato modificato dopo che sono stati convalidati.  
  
 Se il membro è relative alla sicurezza, vengono fornite informazioni utili per creare una copia e quindi convalidare ed elaborare l'argomento.  
  
### <a name="parameter-passing"></a>Passaggio dei parametri  
 Dalla prospettiva di una finestra di progettazione di framework, sono disponibili tre gruppi principali di parametri: parametri, dal valore `ref` parametri, e `out` parametri.  
  
 Quando viene passato un argomento tramite un parametro in base al valore, il membro riceve una copia dell'argomento effettivo passato. Se l'argomento è un tipo di valore, una copia dell'argomento viene inserita nello stack. Se l'argomento è un tipo riferimento, una copia del riferimento viene inserita nello stack. Linguaggi di Common Language Runtime più diffusi, ad esempio c#, VB.NET e C++, predefinito per il passaggio di parametri per valore.  
  
 Quando viene passato un argomento tramite un `ref` parametro, il membro riceve un riferimento all'argomento effettivo passato. Se l'argomento è un tipo di valore, viene inserito un riferimento all'argomento nello stack. Se l'argomento è un tipo riferimento, viene inserito un riferimento al riferimento nello stack. `Ref` i parametri utilizzabile per consentire il membro modificare gli argomenti passati dal chiamante.  
  
 `Out` i parametri sono simili a `ref` parametri, con alcune piccole differenze. Il parametro verrà considerato inizialmente non assegnati e non possono essere letti nel corpo del membro prima che venga assegnata a un valore. Inoltre, il parametro deve essere assegnato un valore prima che venga restituito il membro.  
  
 **X AVOID** mediante `out` o `ref` parametri.  
  
 Usando `out` o `ref` parametri richiede esperienza nell'utilizzo dei puntatori, informazioni sulle differiscano tra i tipi di valore e tipi di riferimento e gestione dei metodi con più valori restituiti. Inoltre, la differenza tra `out` e `ref` parametri non è stato ampiamente riconosciuto. Gli architetti di Framework progettazione per un pubblico generico non possono prevedere agli utenti di utilizzare i `out` o `ref` parametri.  
  
 **X DO NOT** passare i tipi di riferimento per riferimento.  
  
 Esistono alcune eccezioni alla regola, ad esempio un metodo che può essere utilizzato per scambiare i riferimenti.  
  
### <a name="members-with-variable-number-of-parameters"></a>Membri con un numero variabile di parametri  
 I membri che possono accettare un numero variabile di argomenti sono espressi fornendo un parametro di matrice. Ad esempio, <xref:System.String> fornisce il metodo seguente:  
  
```  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 Un utente può quindi chiamare il <xref:System.String.Format%2A?displayProperty=nameWithType> (metodo), come indicato di seguito:  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 Aggiunta la parola chiave params c# a un parametro di matrice viene modificato il parametro a un parametro di matrice cosiddette params e fornisce un collegamento per la creazione di una matrice temporanea.  
  
```  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 In questo modo consente all'utente di chiamare il metodo passando gli elementi della matrice direttamente nell'elenco di argomenti.  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 Si noti che è possibile aggiungere la parola chiave params solo all'ultimo parametro nell'elenco dei parametri.  
  
 **✓ CONSIDER** aggiungendo la parola chiave params ai parametri di matrice, se si prevede che gli utenti finali per passare matrici con un numero limitato di elementi. Se si prevede che un numero elevato di elementi verrà passato in comune scenari, gli utenti probabilmente non supera tali elementi inline comunque e pertanto non è necessaria la parola chiave params.  
  
 **X AVOID** utilizzo delle matrici di parametri se il chiamante quasi sempre necessario l'input già in una matrice.  
  
 Ad esempio, i membri con i parametri di matrice di byte non verrebbero quasi mai essere chiamati passando byte singoli. Per questo motivo, i parametri di matrice di byte in .NET Framework non usano la parola chiave params.  
  
 **X DO NOT** utilizzare matrici params se la matrice viene modificata dal membro che accetta il parametro di matrice di parametri.  
  
 A causa del fatto che molti compilatori trasformare gli argomenti per il membro in una matrice temporanea nel sito di chiamata, la matrice potrebbe essere un oggetto temporaneo e pertanto alcuna modifica alla matrice andranno perse.  
  
 **✓ CONSIDER** utilizzando la parola chiave params in un overload semplice, anche se un overload più complesso non è stato possibile utilizzarla.  
  
 Chiedersi se gli utenti sarebbero valore la presenza di una matrice di parametri in uno degli overload anche se non è stato in tutti gli overload.  
  
 **✓ DO** tenta di ordinare i parametri per consentono di utilizzare la parola chiave params.  
  
 **✓ CONSIDER** fornendo overload speciali e i percorsi del codice per le chiamate con un numero ridotto di argomenti nelle API molto sensibili alle prestazioni.  
  
 Questo rende possibile per evitare di creare gli oggetti matrice quando viene chiamata l'API con un numero ridotto di argomenti. Costituiscono i nomi dei parametri prendendo una forma singolare del parametro della matrice e aggiunta di un suffisso numerico.  
  
 È consigliabile farlo solo se si intende specialistico il percorso di codice completo, non è sufficiente creare una matrice e chiamare il metodo più generico.  
  
 **✓ DO** tenere presente che null è stato passato come argomento di matrice di parametri.  
  
 È necessario convalidare che la matrice non è null prima dell'elaborazione.  
  
 **X DO NOT** usare il `varargs` metodi, altrimenti noti come i puntini di sospensione.  
  
 Alcuni linguaggi CLR, ad esempio C++, supportano una convenzione alternativa per il passaggio di elenchi di parametri variabile denominati `varargs` metodi. La convenzione non deve essere utilizzata nei Framework, perché non è conforme a CLS.  
  
### <a name="pointer-parameters"></a>Parametri dei puntatori  
 In generale, i puntatori non devono essere visualizzati nell'area di superficie di un framework progettato correttamente il codice gestito. La maggior parte dei casi, i puntatori devono essere incapsulati. Tuttavia, in alcuni casi sono necessari per motivi di interoperabilità tra i puntatori e l'uso di puntatori in questi casi è appropriato.  
  
 **✓ DO** forniscono un'alternativa per i membri che accetta un argomento di puntatore, poiché i puntatori non sono conformi a CLS.  
  
 **X AVOID** in questo argomento costoso il controllo degli argomenti del puntatore.  
  
 **✓ DO** convenzioni comuni correlati puntatore quando si progettano i membri con puntatori.  
  
 Ad esempio, non è necessario passare l'indice di inizio, perché l'aritmetica dei puntatori semplice può essere utilizzata per ottenere lo stesso risultato.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
