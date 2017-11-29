---
title: Progettazione di parametri
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7d49c4263517830f46b1416684c7d9b874cda4db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="parameter-design"></a>Progettazione di parametri
In questa sezione fornisce linee guida generali sulla progettazione di parametro, incluse sezioni con le linee guida per gli argomenti sul controllo. Inoltre, è consigliabile consultare le linee guida descritte [denominazione dei parametri](../../../docs/standard/design-guidelines/naming-parameters.md).  
  
 **✓ SI** utilizzare il tipo di parametro meno derivato che fornisce la funzionalità richiesta dal membro.  
  
 Si supponga, ad esempio, che si desidera progettare un metodo che enumera una raccolta e la stampa di ogni elemento nella console. Questo metodo deve accettare <xref:System.Collections.IEnumerable> come parametro, non <xref:System.Collections.ArrayList> o <xref:System.Collections.IList>, ad esempio.  
  
 **X non** utilizzare parametri riservati.  
  
 Se più input a un membro è necessaria nelle versioni future, è possibile aggiungere un nuovo overload.  
  
 **X non** sono esposte pubblicamente metodi che accettano puntatori, matrici di puntatori o le matrici multidimensionali come parametri.  
  
 I puntatori e matrici multidimensionali sono relativamente difficili da utilizzare in modo appropriato. Nella quasi totalità dei casi, le API possono essere riprogettate per evitare questi tipi come parametri.  
  
 **✓ SI** inserire tutti `out` parametri che seguono tutti il valore da e `ref` parametri (incluse matrici di parametro), anche se il risultato è un'incoerenza nel parametro ordinamento tra gli overload (vedere [membro L'overload](../../../docs/standard/design-guidelines/member-overloading.md)).  
  
 Il `out` parametri possono essere visualizzati come valori di ritorno a capo e raggruppandoli rende la firma del metodo più facile da comprendere.  
  
 **✓ SI** sia sempre coerente denominazione dei parametri quando si esegue l'override di membri o di implementazione di membri di interfaccia.  
  
 Questo comunica meglio la relazione tra i metodi.  
  
### <a name="choosing-between-enum-and-boolean-parameters"></a>Scelta tra i parametri booleani e di enumerazione  
 **✓ SI** utilizzare enumerazioni se un membro in caso contrario sarebbe due o più parametri booleani.  
  
 **X non** utilizzare valori booleani, a meno che non si è assolutamente certi non sarà mai necessario per più di due valori.  
  
 Le enumerazioni consentono di spazio per future aggiunta di valori, ma è necessario essere consapevoli di tutte le implicazioni dell'aggiunta di valori per le enumerazioni, che sono descritte nel [progettazione Enum](../../../docs/standard/design-guidelines/enum.md).  
  
 **Provare a ✓** utilizzando i valori booleani per i parametri del costruttore che sono realmente due stati, valori e vengono utilizzati per inizializzare le proprietà booleane.  
  
### <a name="validating-arguments"></a>Convalida di argomenti  
 **✓ SI** convalidare gli argomenti passati ai membri pubblici, protetti o implementati in modo esplicito. Generare <xref:System.ArgumentException?displayProperty=nameWithType>, o una delle sue sottoclassi, se la convalida non riesce.  
  
 Si noti che la convalida effettiva non deve necessariamente essere eseguita con il membro pubblico o protetto stesso. Problema può verificarsi a un livello inferiore in alcune routine privato o interno. Il punto principale è che l'intera superficie esposta agli utenti finali controlla gli argomenti.  
  
 **✓ SI** generare <xref:System.ArgumentNullException> se viene passato un argomento null e il membro non supporta argomenti null.  
  
 **✓ SI** convalidare i parametri enum.  
  
 Si presuppone l'enum argomenti sarà nell'intervallo definito dal tipo enum. CLR consente di eseguire il cast di qualsiasi valore intero in un valore di enumerazione, anche se il valore non è definito nell'enumerazione.  
  
 **X non** utilizzare <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> per intervallo di enumerazione controlla.  
  
 **✓ SI** tenere presente che gli argomenti modificabili sia stato modificato dopo che sono stati convalidati.  
  
 Se il membro è basata sulla protezione, vengono fornite informazioni utili per creare una copia e quindi convalidare ed elaborare l'argomento.  
  
### <a name="parameter-passing"></a>Passaggio dei parametri  
 Dalla prospettiva di una finestra di progettazione di framework, sono disponibili tre gruppi principali di parametri: parametri per valore `ref` , parametri e `out` parametri.  
  
 Quando viene passato un argomento tramite un parametro per valore, il membro riceve una copia dell'argomento effettivo passato. Se l'argomento è un tipo di valore, una copia dell'argomento viene inserita nello stack. Se l'argomento è un tipo riferimento, una copia del riferimento viene inserita nello stack. Lingue CLR più diffusi, ad esempio c#, Visual Basic.NET e C++, predefinito per il passaggio di parametri per valore.  
  
 Quando viene passato un argomento tramite una `ref` parametro, il membro riceve un riferimento all'argomento effettivo passato. Se l'argomento è un tipo di valore, viene inserito un riferimento all'argomento nello stack. Se l'argomento è un tipo riferimento, un riferimento al riferimento viene inserito nello stack. `Ref`parametri possono essere utilizzati per consentire il membro modificare gli argomenti passati dal chiamante.  
  
 `Out`i parametri sono simili a `ref` parametri, con alcune piccole differenze. Il parametro è considerato inizialmente non assegnato e non può essere letto nel corpo del membro prima che venga assegnata a un valore. Inoltre, il parametro deve essere assegnato un valore prima che venga restituito il membro.  
  
 **X evitare** utilizzando `out` o `ref` parametri.  
  
 Utilizzando `out` o `ref` parametri richiede esperienza nell'utilizzo dei puntatori, conoscenza delle differenziano tra tipi di valore e tipi di riferimento e dei metodi con più valori restituiti. Inoltre, la differenza tra `out` e `ref` parametri non è sempre nota. Architetti Framework progettazione per un pubblico generico non possono prevedere gli utenti in grado di utilizzare i `out` o `ref` parametri.  
  
 **X non** passare tipi riferimento per riferimento.  
  
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
  
 Aggiunta la parola chiave params c# a un parametro di matrice viene modificato il parametro a un parametro di matrice params cosiddetti e fornisce un collegamento per la creazione di una matrice temporanea.  
  
```  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 Questa operazione consente all'utente di chiamare il metodo passando gli elementi della matrice direttamente nell'elenco di argomenti.  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 Si noti che è possibile aggiungere la parola chiave params solo all'ultimo parametro nell'elenco di parametri.  
  
 **Provare a ✓** aggiungendo la parola chiave params ai parametri di matrice, se si prevede che gli utenti finali di passare le matrici con un numero limitato di elementi. Se si prevede che un numero elevato di elementi verrà passato in comune scenari, gli utenti probabilmente non supera tali elementi inline comunque e pertanto non è necessaria la parola chiave params.  
  
 **X evitare** utilizzo delle matrici di parametri se il chiamante quasi sempre necessario l'input già in una matrice.  
  
 Ad esempio, i membri con i parametri di matrice di byte non sarebbero quasi mai essere chiamati passando byte singoli. Per questo motivo, i parametri di matrice di byte in .NET Framework non utilizzano la parola chiave params.  
  
 **X non** utilizzare matrici params se la matrice viene modificata dal membro che accetta il parametro di matrice di parametri.  
  
 Per il motivo è che molti compilatori gli argomenti per il membro in una matrice temporanea nel sito di chiamata, la matrice potrebbe essere un oggetto temporaneo e pertanto le modifiche alla matrice andranno persi.  
  
 **Provare a ✓** utilizzando la parola chiave params in un overload semplice, anche se potrebbe non utilizza un overload più complesso.  
  
 È necessario stabilire se gli utenti sarebbero valore con la matrice di parametri in uno degli overload anche se non è stato in tutti gli overload.  
  
 **✓ SI** tenta di ordinare i parametri per consentire di utilizzare la parola chiave params.  
  
 **Provare a ✓** fornendo overload speciali e i percorsi del codice per le chiamate con un numero limitato di argomenti nelle API molto sensibili alle prestazioni.  
  
 In questo modo evitare di creare oggetti matrice quando viene chiamata l'API con un numero limitato di argomenti. Richiede una forma singolare del parametro di matrice e aggiungendo un suffisso numerico, formano i nomi dei parametri.  
  
 Si deve essere eseguita solo se si sta per l'intero percorso del codice speciale, non è sufficiente creare una matrice e chiamare il metodo più generale.  
  
 **✓ SI** tenere presente che null può essere passato come argomento di matrice di parametri.  
  
 È necessario convalidare che la matrice non sia null prima dell'elaborazione.  
  
 **X non** utilizzare il `varargs` metodi, altrimenti noti come i puntini di sospensione.  
  
 Alcuni linguaggi CLR, ad esempio C++, supportano una convenzione alternativa per il passaggio di elenchi di parametri variabile denominati `varargs` metodi. La convenzione di non utilizzare nel Framework, perché non è conforme a CLS.  
  
### <a name="pointer-parameters"></a>Parametri dei puntatori  
 In generale, i puntatori non devono essere visualizzati nell'area della superficie pubblica di un framework di codice gestito ben progettata. La maggior parte dei casi, i puntatori devono essere incapsulati. Tuttavia, in alcuni casi i puntatori sono necessari per motivi di interoperabilità e utilizza i puntatori in questi casi è appropriato.  
  
 **✓ SI** forniscono un'alternativa per i membri che accetta un argomento di puntatore, poiché i puntatori non sono conformi a CLS.  
  
 **X evitare** in questo argomento costoso il controllo degli argomenti del puntatore.  
  
 **✓ SI** convenzioni comuni correlati al puntatore quando si progettano i membri con puntatori.  
  
 Ad esempio, è necessario passare l'indice di inizio, poiché è possibile utilizzare l'aritmetica dei puntatori semplice per ottenere lo stesso risultato.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida di progettazione di membro](../../../docs/standard/design-guidelines/member.md)  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
