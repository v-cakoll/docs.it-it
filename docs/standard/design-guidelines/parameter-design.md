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
ms.openlocfilehash: 93554594b49b742a6a5e8461b6b16046701ec07c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347845"
---
# <a name="parameter-design"></a>Progettazione di parametri

In questa sezione vengono fornite linee guida generali sulla progettazione dei parametri, incluse le sezioni con linee guida per il controllo degli argomenti. Inoltre, è necessario fare riferimento alle linee guida descritte in [denominazione dei parametri](../../../docs/standard/design-guidelines/naming-parameters.md).  
  
 **✓ DO** utilizzare il tipo di parametro meno derivato che fornisce le funzionalità richieste da un membro.  
  
 Si supponga, ad esempio, di voler progettare un metodo che enumera una raccolta e stampa ogni elemento nella console. Questo metodo deve prendere <xref:System.Collections.IEnumerable> come parametro, non <xref:System.Collections.ArrayList> o <xref:System.Collections.IList>, ad esempio.  
  
 **X DO NOT** utilizzare parametri riservati.  
  
 Se in una versione futura è necessario più input per un membro, è possibile aggiungere un nuovo overload.  
  
 **X DO NOT** sono esposte pubblicamente i metodi che accettano puntatori, matrici di puntatori o le matrici multidimensionali come parametri.  
  
 I puntatori e le matrici multidimensionali sono relativamente difficili da utilizzare correttamente. In quasi tutti i casi, le API possono essere riprogettate per evitare di assumere questi tipi come parametri.  
  
 **✓ DO** inserire tutti `out` parametri che seguono tutti il base al valore e `ref` parametri (esclusi matrici di parametro), anche se il risultato è un'incoerenza nel parametro ordinamento viene eseguito tra gli overload (vedere [membro L'overload](../../../docs/standard/design-guidelines/member-overloading.md)).  
  
 I parametri di `out` possono essere considerati come valori restituiti aggiuntivi e la loro raggruppamento rende la firma del metodo più semplice da comprendere.  
  
 **✓ DO** sia sempre coerente denominazione dei parametri quando si esegue l'override di membri o di implementazione di membri di interfaccia.  
  
 Ciò comunicherà meglio la relazione tra i metodi.  
  
### <a name="choose-between-enum-and-boolean-parameters"></a>Scegliere tra i parametri enum e Boolean  
 **✓ DO** utilizzare enumerazioni se un membro in caso contrario sarebbe due o più parametri booleani.  
  
 **X DO NOT** utilizzare valori booleani, a meno che non si è assolutamente certi non sarà mai necessario per più di due valori.  
  
 Le enumerazioni forniscono una certa spazio per l'aggiunta futura di valori, ma è necessario tenere presenti tutte le implicazioni dell'aggiunta di valori alle enumerazioni, descritte in [enum design](../../../docs/standard/design-guidelines/enum.md).  
  
 **✓ CONSIDER** utilizzando valori booleani per i parametri del costruttore che sono realmente due stati, valori e vengono utilizzati per inizializzare le proprietà booleane.  
  
### <a name="validate-arguments"></a>Convalida argomenti  
 **✓ DO** convalidare gli argomenti passati ai membri pubblici, protetti o implementati in modo esplicito. Genera <xref:System.ArgumentException?displayProperty=nameWithType>o una delle relative sottoclassi se la convalida ha esito negativo.  
  
 Si noti che la convalida effettiva non deve necessariamente essere eseguita nel membro pubblico o protetto. Potrebbe verificarsi a un livello inferiore in una routine privata o interna. Il punto principale è che l'intera superficie esposta agli utenti finali controlla gli argomenti.  
  
 **✓ DO** throw <xref:System.ArgumentNullException> se viene passato un argomento null e il membro non supporta argomenti null.  
  
 **✓ DO** convalidare i parametri enum.  
  
 Non presupporre che gli argomenti enum siano compresi nell'intervallo definito dall'enumerazione. CLR consente il cast di qualsiasi valore intero in un valore enum anche se il valore non è definito nell'enumerazione.  
  
 **X DO NOT** utilizzare <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> per intervallo di enumerazione controlla.  
  
 **✓ DO** tenere presente che gli argomenti modificabili sia stato modificato dopo che sono stati convalidati.  
  
 Se il membro è sensibile alla sicurezza, è consigliabile creare una copia e quindi convalidare ed elaborare l'argomento.  
  
### <a name="pass-parameters"></a>Passare parametri  
 Dal punto di vista di una finestra di progettazione del Framework, sono disponibili tre gruppi principali di parametri: parametri per valore, parametri di `ref` e parametri di `out`.  
  
 Quando un argomento viene passato tramite un parametro per valore, il membro riceve una copia dell'argomento effettivo passato. Se l'argomento è un tipo valore, viene inserita una copia dell'argomento nello stack. Se l'argomento è un tipo di riferimento, viene inserita una copia del riferimento nello stack. I linguaggi CLR più diffusi, ad C#esempio Visual Basic e C++, per impostazione predefinita passano i parametri per valore.  
  
 Quando un argomento viene passato tramite un parametro di `ref`, il membro riceve un riferimento all'argomento effettivo passato. Se l'argomento è un tipo valore, viene inserito un riferimento all'argomento nello stack. Se l'argomento è un tipo di riferimento, nello stack viene inserito un riferimento al riferimento. è possibile utilizzare i parametri `Ref` per consentire al membro di modificare gli argomenti passati dal chiamante.  
  
 `Out` parametri sono simili ai parametri `ref`, con alcune piccole differenze. Il parametro viene inizialmente considerato non assegnato e non può essere letto nel corpo del membro prima che venga assegnato un valore. Inoltre, è necessario assegnare un valore al parametro prima che il membro restituisca.  
  
 **X AVOID** mediante `out` o `ref` parametri.  
  
 Per usare i parametri `out` o `ref` è necessaria un'esperienza con i puntatori, informazioni sulla differenza tra tipi di valore e tipi di riferimento e metodi di gestione con più valori restituiti. Inoltre, la differenza tra `out` e i parametri di `ref` non è ampiamente riconosciuta. Gli architetti di Framework che progettano i destinatari generali non dovrebbero aspettarsi che gli utenti lavorino con `out` o `ref` parametri.  
  
 **X DO NOT** passare i tipi di riferimento per riferimento.  
  
 Esistono alcune eccezioni limitate alla regola, ad esempio un metodo che può essere usato per scambiare i riferimenti.  
  
### <a name="members-with-variable-number-of-parameters"></a>Membri con numero variabile di parametri  
 I membri che possono assumere un numero variabile di argomenti vengono espressi fornendo un parametro di matrice. Ad esempio, <xref:System.String> fornisce il metodo seguente:  
  
```csharp  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 Un utente può quindi chiamare il metodo <xref:System.String.Format%2A?displayProperty=nameWithType>, come indicato di seguito:  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 Se si C# aggiunge la parola chiave params a un parametro di matrice, il parametro viene modificato in un parametro di matrice denominato params e viene fornito un collegamento per la creazione di una matrice temporanea.  
  
```csharp  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 Questa operazione consente all'utente di chiamare il metodo passando gli elementi della matrice direttamente nell'elenco di argomenti.  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 Si noti che la parola chiave params può essere aggiunta solo all'ultimo parametro nell'elenco di parametri.  
  
 **✓ CONSIDER** aggiungendo la parola chiave params ai parametri di matrice, se si prevede che gli utenti finali per passare matrici con un numero limitato di elementi. Se si prevede che molti elementi vengano passati negli scenari comuni, gli utenti probabilmente non passano questi elementi inline, quindi la parola chiave params non è necessaria.  
  
 **X AVOID** utilizzo delle matrici di parametri se il chiamante quasi sempre necessario l'input già in una matrice.  
  
 I membri con parametri di matrice di byte, ad esempio, non vengono mai chiamati passando singoli byte. Per questo motivo, i parametri della matrice di byte nel .NET Framework non usano la parola chiave params.  
  
 **X DO NOT** utilizzare matrici params se la matrice viene modificata dal membro che accetta il parametro di matrice di parametri.  
  
 Poiché molti compilatori trasformano gli argomenti nel membro in una matrice temporanea nel sito di chiamata, la matrice potrebbe essere un oggetto temporaneo e pertanto le modifiche apportate alla matrice andranno perse.  
  
 **✓ CONSIDER** utilizzando la parola chiave params in un overload semplice, anche se un overload più complesso non è stato possibile utilizzarla.  
  
 Chiedere se gli utenti hanno valore con la matrice params in un overload anche se non era in tutti gli overload.  
  
 **✓ DO** tenta di ordinare i parametri per consentono di utilizzare la parola chiave params.  
  
 **✓ CONSIDER** fornendo overload speciali e i percorsi del codice per le chiamate con un numero ridotto di argomenti nelle API molto sensibili alle prestazioni.  
  
 In questo modo è possibile evitare la creazione di oggetti Array quando l'API viene chiamata con un numero ridotto di argomenti. Formare i nomi dei parametri prendendo una forma singolare del parametro di matrice e aggiungendo un suffisso numerico.  
  
 Questa operazione deve essere eseguita solo se si intende usare in modo speciale l'intero percorso del codice, non solo creare una matrice e chiamare il metodo più generale.  
  
 **✓ DO** tenere presente che null è stato passato come argomento di matrice di parametri.  
  
 Prima di eseguire l'elaborazione, è necessario verificare che la matrice non sia null.  
  
 **X DO NOT** usare il `varargs` metodi, altrimenti noti come i puntini di sospensione.  
  
 Alcuni linguaggi CLR, ad esempio C++, supportano una convenzione alternativa per passare elenchi di parametri variabili denominati `varargs` metodi. La convenzione non deve essere utilizzata nei Framework, perché non è conforme a CLS.  
  
### <a name="pointer-parameters"></a>Parametri del puntatore  
 In generale, i puntatori non devono essere visualizzati nella superficie pubblica di un Framework di codice gestito ben progettato. Nella maggior parte dei casi, i puntatori devono essere incapsulati. In alcuni casi, tuttavia, i puntatori sono necessari per motivi di interoperabilità e l'utilizzo di puntatori in tali casi è appropriato.  
  
 **✓ DO** forniscono un'alternativa per i membri che accetta un argomento di puntatore, poiché i puntatori non sono conformi a CLS.  
  
 **X AVOID** in questo argomento costoso il controllo degli argomenti del puntatore.  
  
 **✓ DO** convenzioni comuni correlati puntatore quando si progettano i membri con puntatori.  
  
 Ad esempio, non è necessario passare l'indice iniziale, perché per ottenere lo stesso risultato è possibile utilizzare l'aritmetica semplice del puntatore.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
