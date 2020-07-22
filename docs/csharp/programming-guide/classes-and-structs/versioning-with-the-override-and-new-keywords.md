---
title: Controllo delle versioni con le parole chiave Override e New - Guida per programmatori C#
description: Informazioni sul controllo delle versioni per le classi base e derivate in C# e su come specificare se un metodo deve eseguire l'override o nascondere un metodo ereditato.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, versioning
- C# language, override and new
ms.assetid: 88247d07-bd0d-49e9-a619-45ccbbfdf0c5
ms.openlocfilehash: c2630741e1055a14dd5b9e4445d660cfd68891b0
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86863864"
---
# <a name="versioning-with-the-override-and-new-keywords-c-programming-guide"></a>Controllo delle versioni con le parole chiave Override e New (Guida per programmatori C#)
Il linguaggio C# è progettato in modo che il controllo delle versioni tra le classi [di base](../../language-reference/keywords/base.md) e le classi derivate in diverse librerie possa svilupparsi e mantenere la compatibilità con le versioni precedenti. Ciò significa ad esempio che l'introduzione di un nuovo membro in una classe [di base](../../language-reference/keywords/class.md) con lo stesso nome di un membro in una classe derivata è completamente supportata da C# e non causa comportamenti imprevisti. Significa inoltre che una classe deve dichiarare in modo esplicito se un metodo deve eseguire l'override di un metodo ereditato o se si tratta di un nuovo metodo che consente di nascondere un metodo ereditato con nome simile.  
  
 In C# le classi derivate possono contenere metodi con lo stesso nome dei metodi delle classi di base.  

- Se il metodo della classe derivata non è preceduto dalle parole chiave [new](../../language-reference/keywords/new-modifier.md) o [override](../../language-reference/keywords/override.md), il compilatore genera un avviso e il metodo si comporta come se fosse presente la parola chiave `new`.  
  
- Se il metodo della classe derivata è preceduto dalla parola chiave `new`, il metodo è definito come indipendente dal metodo della classe di base.  
  
- Se il metodo della classe derivata è preceduto dalla parola chiave `override`, gli oggetti della classe derivata chiameranno tale metodo anziché il metodo della classe di base.  

- Per applicare la `override` parola chiave al metodo nella classe derivata, il metodo della classe base deve essere definito come [Virtual](../../language-reference/keywords/virtual.md).
  
- Il metodo della classe di base può essere chiamato dall'interno della classe derivata usando la parola chiave `base`.  
  
- Le parole chiave `override`, `virtual` e `new` possono essere applicate anche a proprietà, indicizzatori ed eventi.  
  
 Per impostazione predefinita, i metodi C# non sono virtuali. Se un metodo viene dichiarato come virtuale, qualsiasi classe che eredita il metodo può implementare la propria versione. Per rendere un metodo virtuale, si usa il modificatore `virtual` nella dichiarazione del metodo della classe di base. La classe derivata può quindi eseguire l'override del metodo di base virtuale usando la parola chiave `override` oppure nascondere il metodo virtuale nella classe di base usando la parola chiave `new`. Se non si specifica né la parola chiave `override` né la parola chiave `new`, il compilatore genera un avviso e il metodo della classe derivata nasconde il metodo della classe di base.  
  
 Per dimostrare questo concetto in pratica, si supponga che la società A abbia creato una classe denominata `GraphicsClass` che viene usata dal programma. Di seguito è illustrata la classe `GraphicsClass`:  
  
 [!code-csharp[csProgGuideInheritance#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#27)]  
  
 La società usa questa classe e l'utente la usa per derivare la propria classe, aggiungendo un nuovo metodo:  
  
 [!code-csharp[csProgGuideInheritance#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#28)]  
  
 L'applicazione viene eseguita senza problemi, finché la società A rilascia una nuova versione di `GraphicsClass`, simile al codice seguente:  
  
 [!code-csharp[csProgGuideInheritance#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#29)]  
  
 La nuova versione di `GraphicsClass` ora contiene un metodo denominato `DrawRectangle`. Inizialmente non accade nulla. La nuova versione è ancora compatibile a livello binario con la versione precedente. Qualsiasi software già distribuito continuerà a funzionare, anche se la nuova classe viene installata nei relativi computer. Le eventuali chiamate al metodo `DrawRectangle` continueranno a fare riferimento alla versione in uso nella classe derivata.  
  
 Tuttavia, non appena l'applicazione viene ricompilata usando la nuova versione di `GraphicsClass`, si riceve un avviso del compilatore, CS0108. L'avviso informa che è necessario stabilire in che modo dovrà funzionare il metodo `DrawRectangle` nell'applicazione.  
  
 Se il metodo deve eseguire l'override del nuovo metodo della classe di base, usare la parola chiave `override`:  
  
 [!code-csharp[csProgGuideInheritance#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#30)]  
  
 La parola chiave `override` garantisce che qualsiasi oggetto derivato da `YourDerivedGraphicsClass` userà la versione della classe derivata di `DrawRectangle`. Gli oggetti derivati da `YourDerivedGraphicsClass` possono comunque accedere alla versione della classe di base `DrawRectangle` usando la parola chiave di base:  
  
 [!code-csharp[csProgGuideInheritance#44](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#44)]  
  
 Se si preferisce che il metodo non esegua l'override del nuovo metodo della classe di base, attenersi alle indicazioni che seguono. Per evitare confusione tra i due metodi, è possibile rinominare il metodo da usare. Questa operazione può richiedere molto tempo e causare errori e in alcuni casi è poco pratica. Tuttavia, se il progetto è relativamente piccolo, è possibile usare le opzioni di refactoring di Visual Studio per rinominare il metodo. Per altre informazioni, vedere [Refactoring di classi e tipi (Progettazione classi)](/visualstudio/ide/class-designer/refactoring-classes-and-types).  
  
 In alternativa, è possibile evitare l'avviso usando la parola chiave `new` nella definizione della classe derivata:  
  
 [!code-csharp[csProgGuideInheritance#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#31)]  
  
 L'uso della parola chiave `new` indica al compilatore che la definizione nasconde la definizione contenuta nella classe di base. Questo è il comportamento predefinito.  
  
## <a name="override-and-method-selection"></a>Override e selezione del metodo  
 Quando un metodo è denominato in una classe, il compilatore C# seleziona il metodo migliore per la chiamata se più metodi sono compatibili con la chiamata, ad esempio quando esistono due metodi con lo stesso nome e parametri compatibili con il parametro passato. I seguenti metodi sarebbero compatibili:  
  
 [!code-csharp[csProgGuideInheritance#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#32)]  
  
 Quando si chiama `DoWork` per un'istanza di `Derived`, il compilatore C# tenta per prima cosa di rendere la chiamata compatibile con le versioni di `DoWork` originariamente dichiarate in `Derived`. I metodi di override non vengono considerati come dichiarati per una classe, sono nuove implementazioni di un metodo dichiarato per una classe di base. Solo se il compilatore C# non è in grado di associare la chiamata al metodo a un metodo originale in `Derived`, tenterà di associare la chiamata a un metodo sottoposto a override con lo stesso nome e parametri compatibili. ad esempio:  
  
 [!code-csharp[csProgGuideInheritance#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#33)]  
  
 Poiché la variabile `val` può essere convertita in un valore double in modo implicito, il compilatore C# chiama `DoWork(double)` anziché `DoWork(int)`. Questa situazione può essere evitata in due modi. Primo, evitare di dichiarare i nuovi metodi con lo stesso nome dei metodi virtuali. Secondo, è possibile indicare al compilatore C# di chiamare il metodo virtuale facendo in modo che esegua una ricerca nell'elenco dei metodi della classe di base eseguendo il cast dell'istanza di `Derived` a `Base`. Poiché il metodo è virtuale, verrà chiamata l'implementazione di `DoWork(int)` per `Derived`. ad esempio:  
  
 [!code-csharp[csProgGuideInheritance#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#34)]  
  
 Per altri esempi di `new` e `override`, vedere [Sapere quando usare le parole chiave Override e New](./knowing-when-to-use-override-and-new-keywords.md).  
  
## <a name="see-also"></a>Vedi anche

- [Guida per programmatori C#](../index.md)
- [Classi e struct](./index.md)
- [Metodi](./methods.md)
- [Ereditarietà](./inheritance.md)
