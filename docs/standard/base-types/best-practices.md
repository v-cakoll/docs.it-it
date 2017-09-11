---
title: Procedure consigliate per le espressioni regolari
description: Procedure consigliate per le espressioni regolari
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 096fd614-91bf-4296-be24-12f62b062294
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: cf9c83de791fa4990a991689a26d4bbdd84cfe7d
ms.contentlocale: it-it
ms.lasthandoff: 03/02/2017

---

# <a name="best-practices-for-regular-expressions"></a><span data-ttu-id="93303-104">Procedure consigliate per le espressioni regolari</span><span class="sxs-lookup"><span data-stu-id="93303-104">Best practices for regular expressions</span></span>

<span data-ttu-id="93303-105">Il motore delle espressioni regolari in .NET è uno strumento potente e completo che consente di elaborare il testo in base alle corrispondenze dei modelli anziché in base al confronto e alla corrispondenza con il testo letterale.</span><span class="sxs-lookup"><span data-stu-id="93303-105">The regular expression engine in .NET is a powerful, full-featured tool that processes text based on pattern matches rather than on comparing and matching literal text.</span></span> <span data-ttu-id="93303-106">Nella maggior parte dei casi, la corrispondenza dei modelli viene applicata in modo rapido ed efficiente.</span><span class="sxs-lookup"><span data-stu-id="93303-106">In most cases, it performs pattern matching rapidly and efficiently.</span></span> <span data-ttu-id="93303-107">In alcuni casi, tuttavia, il motore delle espressioni regolari può risultare molto lento.</span><span class="sxs-lookup"><span data-stu-id="93303-107">However, in some cases, the regular expression engine can appear to be very slow.</span></span> <span data-ttu-id="93303-108">In casi estremi, può anche sembrare che il motore non risponda durante l'elaborazione di un input relativamente piccolo per ore o perfino giorni.</span><span class="sxs-lookup"><span data-stu-id="93303-108">In extreme cases, it can even appear to stop responding as it processes a relatively small input over the course of hours or even days.</span></span> 

<span data-ttu-id="93303-109">In questo argomento vengono illustrate alcune procedure consigliate che possono essere adottate dagli sviluppatori per ottenere prestazioni ottimali con le espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="93303-109">This topic outlines some of the best practices that developers can adopt to ensure that their regular expressions achieve optimal performance.</span></span> <span data-ttu-id="93303-110">Include le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="93303-110">It contains the following sections:</span></span>

* [<span data-ttu-id="93303-111">Esaminare l'origine di input</span><span class="sxs-lookup"><span data-stu-id="93303-111">Consider the input source</span></span>](#consider-the-input-source)

* [<span data-ttu-id="93303-112">Gestire la creazione di istanze degli oggetti in modo appropriato</span><span class="sxs-lookup"><span data-stu-id="93303-112">Handle object instantiation appropriately</span></span>](#handle-object-instantiation-appropriately)

* [<span data-ttu-id="93303-113">Assumere il controllo del backtracking</span><span class="sxs-lookup"><span data-stu-id="93303-113">Take charge of backtracking</span></span>](#take-charge-of-backtracking)

* [<span data-ttu-id="93303-114">Usare valori di timeout</span><span class="sxs-lookup"><span data-stu-id="93303-114">Use time-out values</span></span>](#use-time-out-values)

* [<span data-ttu-id="93303-115">Eseguire l'acquisizione solo quando necessario</span><span class="sxs-lookup"><span data-stu-id="93303-115">Capture only when necessary</span></span>](#capture-only-when-necessary)

* [<span data-ttu-id="93303-116">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="93303-116">Related topics</span></span>](#related-topics)

## <a name="consider-the-input-source"></a><span data-ttu-id="93303-117">Esaminare l'origine di input</span><span class="sxs-lookup"><span data-stu-id="93303-117">Consider the input source</span></span>

<span data-ttu-id="93303-118">In generale, le espressioni regolari possono accettare due tipi di input: vincolato o non vincolato.</span><span class="sxs-lookup"><span data-stu-id="93303-118">In general, regular expressions can accept two types of input: constrained or unconstrained.</span></span> <span data-ttu-id="93303-119">Per input vincolato si intende un testo che proviene da un'origine conosciuta o affidabile e segue un formato predefinito.</span><span class="sxs-lookup"><span data-stu-id="93303-119">Constrained input is text that originates from a known or reliable source and follows a predefined format.</span></span> <span data-ttu-id="93303-120">Per input non vincolato si intende un testo che proviene da un'origine non inaffidabile, ad esempio un utente Web, e non può seguire un formato predefinito o previsto.</span><span class="sxs-lookup"><span data-stu-id="93303-120">Unconstrained input is text that originates from an unreliable source, such as a web user, and may not follow a predefined or expected format.</span></span>

<span data-ttu-id="93303-121">I modelli di espressione regolare vengono scritti in genere in modo da corrispondere all'input valido,</span><span class="sxs-lookup"><span data-stu-id="93303-121">Regular expression patterns are typically written to match valid input.</span></span> <span data-ttu-id="93303-122">ovvero gli sviluppatori esaminano il testo per il quale desiderano trovare una corrispondenza e scrivono quindi un modello di espressione regolare a esso corrispondente.</span><span class="sxs-lookup"><span data-stu-id="93303-122">That is, developers examine the text that they want to match and then write a regular expression pattern that matches it.</span></span> <span data-ttu-id="93303-123">Gli sviluppatori determinano infine se questo modello richiede una correzione o un'ulteriore elaborazione testandolo con più elementi di input validi.</span><span class="sxs-lookup"><span data-stu-id="93303-123">Developers then determine whether this pattern requires correction or further elaboration by testing it with multiple valid input items.</span></span> <span data-ttu-id="93303-124">Se il modello corrisponde a tutti gli input considerati validi, viene dichiarato pronto per la produzione e può essere incluso in un'applicazione rilasciata.</span><span class="sxs-lookup"><span data-stu-id="93303-124">When the pattern matches all presumed valid inputs, it is declared to be production-ready and can be included in a released application.</span></span> <span data-ttu-id="93303-125">In tal modo, un modello di espressione regolare viene considerato appropriato per la corrispondenza con un input vincolato.</span><span class="sxs-lookup"><span data-stu-id="93303-125">This makes a regular expression pattern suitable for matching constrained input.</span></span> <span data-ttu-id="93303-126">Tuttavia, non verrà considerato appropriato per la corrispondenza con un input non vincolato.</span><span class="sxs-lookup"><span data-stu-id="93303-126">However, it does not make it suitable for matching unconstrained input.</span></span>

<span data-ttu-id="93303-127">Per corrispondere a un input non vincolato, un'espressione regolare deve potere gestire efficientemente tre tipi di testo:</span><span class="sxs-lookup"><span data-stu-id="93303-127">To match unconstrained input, a regular expression must be able to efficiently handle three kinds of text:</span></span>

<span data-ttu-id="93303-128">• Testo che corrisponde al modello di espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="93303-128">• Text that matches the regular expression pattern.</span></span>

<span data-ttu-id="93303-129">• Testo che non corrisponde al modello di espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="93303-129">• Text that does not match the regular expression pattern.</span></span>

<span data-ttu-id="93303-130">• Testo che quasi corrisponde al modello di espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="93303-130">• Text that nearly matches the regular expression pattern.</span></span>

<span data-ttu-id="93303-131">L'ultimo tipo di testo è particolarmente problematico per un'espressione regolare scritta per gestire l'input vincolato.</span><span class="sxs-lookup"><span data-stu-id="93303-131">The last text type is especially problematic for a regular expression that has been written to handle constrained input.</span></span> <span data-ttu-id="93303-132">Se tale espressione regolare si basa anche sul [backtracking](backtracking.md) esteso, il motore delle espressioni regolari può richiedere una quantità eccessiva di tempo, in alcuni casi molte ore o giorni, per l'elaborazione di un testo apparentemente irrilevante.</span><span class="sxs-lookup"><span data-stu-id="93303-132">If that regular expression also relies on extensive [backtracking](backtracking.md), the regular expression engine can spend an inordinate amount of time (in some cases, many hours or days) processing seemingly innocuous text.</span></span> 

> [!WARNING]
> <span data-ttu-id="93303-133">Nell'esempio seguente viene utilizzata un'espressione regolare soggetta a un backtracking eccessivo e che con tutta probabilità rifiuta indirizzi di posta elettronica validi.</span><span class="sxs-lookup"><span data-stu-id="93303-133">The following example uses a regular expression that is prone to excessive backtracking and that is likely to reject valid email addresses.</span></span> <span data-ttu-id="93303-134">Non utilizzarla in una routine di convalida di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="93303-134">You should not use it in an email validation routine.</span></span> <span data-ttu-id="93303-135">Per un'espressione regolare che convalida gli indirizzi di posta elettronica, vedere [Procedura: Verificare che le stringhe siano in formato di posta elettronica valido](verify-format.md).</span><span class="sxs-lookup"><span data-stu-id="93303-135">If you would like a regular expression that validates email addresses, see [How to: Verify that strings are in valid email format](verify-format.md).</span></span> 


<span data-ttu-id="93303-136">Si consideri, ad esempio, un'espressione regolare comunemente utilizzata ma estremamente problematica per la convalida dell'alias di un indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="93303-136">For example, consider a very commonly used but extremely problematic regular expression for validating the alias of an email address.</span></span> <span data-ttu-id="93303-137">L'espressione regolare `^[0-9A-Z]([-.\w]*[0-9A-Z])*$` viene scritta per elaborare gli indirizzi di posta elettronica ritenuti validi, composti da un carattere alfanumerico seguito da zero o più caratteri che possono essere alfanumerici, punti o trattini.</span><span class="sxs-lookup"><span data-stu-id="93303-137">The regular expression `^[0-9A-Z]([-.\w]*[0-9A-Z])*$` is written to process what is considered to be a valid email address, which consists of an alphanumeric character, followed by zero or more characters that can be alphanumeric, periods, or hyphens.</span></span> <span data-ttu-id="93303-138">L'espressione regolare deve terminare con un carattere alfanumerico.</span><span class="sxs-lookup"><span data-stu-id="93303-138">The regular expression must end with an alphanumeric character.</span></span> <span data-ttu-id="93303-139">Tuttavia, come illustrato nell'esempio seguente, sebbene questa espressione regolare gestisca facilmente l'input valido, le prestazioni risulteranno molto inefficienti quando viene elaborato un input quasi valido.</span><span class="sxs-lookup"><span data-stu-id="93303-139">However, as the following example shows, although this regular expression handles valid input easily, its performance is very inefficient when it is processing nearly valid input.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      Stopwatch sw;    
      string[] addresses = { "AAAAAAAAAAA@contoso.com", 
                             "AAAAAAAAAAaaaaaaaaaa!@contoso.com" };
      // The following regular expression should not actually be used to 
      // validate an email address.
      string pattern = @"^[0-9A-Z]([-.\w]*[0-9A-Z])*$";
      string input; 

      foreach (var address in addresses) {
         string mailBox = address.Substring(0, address.IndexOf("@"));       
         int index = 0;
         for (int ctr = mailBox.Length - 1; ctr >= 0; ctr--) {
            index++;

            input = mailBox.Substring(ctr, index); 
            sw = Stopwatch.StartNew();
            Match m = Regex.Match(input, pattern, RegexOptions.IgnoreCase);
            sw.Stop();
            if (m.Success)
               Console.WriteLine("{0,2}. Matched '{1,25}' in {2}", 
                                 index, m.Value, sw.Elapsed);
            else                     
               Console.WriteLine("{0,2}. Failed  '{1,25}' in {2}", 
                                 index, input, sw.Elapsed);
         }
         Console.WriteLine();
      }
   }
}

// The example displays output similar to the following:
//     1. Matched '                        A' in 00:00:00.0007122
//     2. Matched '                       AA' in 00:00:00.0000282
//     3. Matched '                      AAA' in 00:00:00.0000042
//     4. Matched '                     AAAA' in 00:00:00.0000038
//     5. Matched '                    AAAAA' in 00:00:00.0000042
//     6. Matched '                   AAAAAA' in 00:00:00.0000042
//     7. Matched '                  AAAAAAA' in 00:00:00.0000042
//     8. Matched '                 AAAAAAAA' in 00:00:00.0000087
//     9. Matched '                AAAAAAAAA' in 00:00:00.0000045
//    10. Matched '               AAAAAAAAAA' in 00:00:00.0000045
//    11. Matched '              AAAAAAAAAAA' in 00:00:00.0000045
//    
//     1. Failed  '                        !' in 00:00:00.0000447
//     2. Failed  '                       a!' in 00:00:00.0000071
//     3. Failed  '                      aa!' in 00:00:00.0000071
//     4. Failed  '                     aaa!' in 00:00:00.0000061
//     5. Failed  '                    aaaa!' in 00:00:00.0000081
//     6. Failed  '                   aaaaa!' in 00:00:00.0000126
//     7. Failed  '                  aaaaaa!' in 00:00:00.0000359
//     8. Failed  '                 aaaaaaa!' in 00:00:00.0000414
//     9. Failed  '                aaaaaaaa!' in 00:00:00.0000758
//    10. Failed  '               aaaaaaaaa!' in 00:00:00.0001462
//    11. Failed  '              aaaaaaaaaa!' in 00:00:00.0002885
//    12. Failed  '             Aaaaaaaaaaa!' in 00:00:00.0005780
//    13. Failed  '            AAaaaaaaaaaa!' in 00:00:00.0011628
//    14. Failed  '           AAAaaaaaaaaaa!' in 00:00:00.0022851
//    15. Failed  '          AAAAaaaaaaaaaa!' in 00:00:00.0045864
//    16. Failed  '         AAAAAaaaaaaaaaa!' in 00:00:00.0093168
//    17. Failed  '        AAAAAAaaaaaaaaaa!' in 00:00:00.0185993
//    18. Failed  '       AAAAAAAaaaaaaaaaa!' in 00:00:00.0366723
//    19. Failed  '      AAAAAAAAaaaaaaaaaa!' in 00:00:00.1370108
//    20. Failed  '     AAAAAAAAAaaaaaaaaaa!' in 00:00:00.1553966
//    21. Failed  '    AAAAAAAAAAaaaaaaaaaa!' in 00:00:00.3223372
```

```vb
Imports System.Diagnostics
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim sw As Stopwatch    
      Dim addresses() As String = { "AAAAAAAAAAA@contoso.com", 
                                 "AAAAAAAAAAaaaaaaaaaa!@contoso.com" }
      ' The following regular expression should not actually be used to 
      ' validate an email address.
      Dim pattern As String = "^[0-9A-Z]([-.\w]*[0-9A-Z])*$"
      Dim input As String 

      For Each address In addresses
         Dim mailBox As String = address.Substring(0, address.IndexOf("@"))       
         Dim index As Integer = 0
         For ctr As Integer = mailBox.Length - 1 To 0 Step -1
            index += 1
            input = mailBox.Substring(ctr, index) 
            sw = Stopwatch.StartNew()
            Dim m As Match = Regex.Match(input, pattern, RegexOptions.IgnoreCase)
            sw.Stop()
            if m.Success Then
               Console.WriteLine("{0,2}. Matched '{1,25}' in {2}", 
                                 index, m.Value, sw.Elapsed)
            Else                     
               Console.WriteLine("{0,2}. Failed  '{1,25}' in {2}", 
                                 index, input, sw.Elapsed)
            End If                  
         Next
         Console.WriteLine()
      Next
   End Sub
End Module
' The example displays output similar to the following:
'     1. Matched '                        A' in 00:00:00.0007122
'     2. Matched '                       AA' in 00:00:00.0000282
'     3. Matched '                      AAA' in 00:00:00.0000042
'     4. Matched '                     AAAA' in 00:00:00.0000038
'     5. Matched '                    AAAAA' in 00:00:00.0000042
'     6. Matched '                   AAAAAA' in 00:00:00.0000042
'     7. Matched '                  AAAAAAA' in 00:00:00.0000042
'     8. Matched '                 AAAAAAAA' in 00:00:00.0000087
'     9. Matched '                AAAAAAAAA' in 00:00:00.0000045
'    10. Matched '               AAAAAAAAAA' in 00:00:00.0000045
'    11. Matched '              AAAAAAAAAAA' in 00:00:00.0000045
'    
'     1. Failed  '                        !' in 00:00:00.0000447
'     2. Failed  '                       a!' in 00:00:00.0000071
'     3. Failed  '                      aa!' in 00:00:00.0000071
'     4. Failed  '                     aaa!' in 00:00:00.0000061
'     5. Failed  '                    aaaa!' in 00:00:00.0000081
'     6. Failed  '                   aaaaa!' in 00:00:00.0000126
'     7. Failed  '                  aaaaaa!' in 00:00:00.0000359
'     8. Failed  '                 aaaaaaa!' in 00:00:00.0000414
'     9. Failed  '                aaaaaaaa!' in 00:00:00.0000758
'    10. Failed  '               aaaaaaaaa!' in 00:00:00.0001462
'    11. Failed  '              aaaaaaaaaa!' in 00:00:00.0002885
'    12. Failed  '             Aaaaaaaaaaa!' in 00:00:00.0005780
'    13. Failed  '            AAaaaaaaaaaa!' in 00:00:00.0011628
'    14. Failed  '           AAAaaaaaaaaaa!' in 00:00:00.0022851
'    15. Failed  '          AAAAaaaaaaaaaa!' in 00:00:00.0045864
'    16. Failed  '         AAAAAaaaaaaaaaa!' in 00:00:00.0093168
'    17. Failed  '        AAAAAAaaaaaaaaaa!' in 00:00:00.0185993
'    18. Failed  '       AAAAAAAaaaaaaaaaa!' in 00:00:00.0366723
'    19. Failed  '      AAAAAAAAaaaaaaaaaa!' in 00:00:00.1370108
'    20. Failed  '     AAAAAAAAAaaaaaaaaaa!' in 00:00:00.1553966
'    21. Failed  '    AAAAAAAAAAaaaaaaaaaa!' in 00:00:00.3223372
```

<span data-ttu-id="93303-140">Come illustrato nell'output dell'esempio, il motore delle espressioni regolari elabora l'alias di posta elettronica valido nello stesso intervallo di tempo indipendentemente dalla lunghezza.</span><span class="sxs-lookup"><span data-stu-id="93303-140">As the output from the example shows, the regular expression engine processes the valid email alias in about the same time interval regardless of its length.</span></span> <span data-ttu-id="93303-141">D'altra parte, quando l'indirizzo di posta elettronica quasi valido ha più di cinque caratteri, il tempo di elaborazione raddoppia approssimativamente per ogni carattere aggiuntivo nella stringa.</span><span class="sxs-lookup"><span data-stu-id="93303-141">On the other hand, when the nearly valid email address has more than five characters, processing time approximately doubles for each additional character in the string.</span></span> <span data-ttu-id="93303-142">Ciò significa che l'elaborazione di una stringa di 28 caratteri quasi valida richiederebbe più di un'ora e l'elaborazione di una stringa di 33 caratteri quasi valida richiederebbe quasi un giorno.</span><span class="sxs-lookup"><span data-stu-id="93303-142">This means that a nearly valid 28-character string would take over an hour to process, and a nearly valid 33-character string would take nearly a day to process.</span></span> 

<span data-ttu-id="93303-143">Poiché questa espressione regolare è stata sviluppata considerando unicamente la corrispondenza con il formato di input, l'input che non corrisponde al modello non viene preso in considerazione.</span><span class="sxs-lookup"><span data-stu-id="93303-143">Because this regular expression was developed solely by considering the format of input to be matched, it fails to take account of input that does not match the pattern.</span></span> <span data-ttu-id="93303-144">Di conseguenza, è possibile consentire a un input non vincolato che corrisponde quasi al modello di espressione regolare di ridurre significativamente le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="93303-144">This, in turn, can allow unconstrained input that nearly matches the regular expression pattern to significantly degrade performance.</span></span>

<span data-ttu-id="93303-145">Per risolvere tale problema, è possibile effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="93303-145">To solve this problem, you can do the following:</span></span>

* <span data-ttu-id="93303-146">Durante lo sviluppo di un modello, è consigliabile considerare il modo in cui il backtracking potrebbe influire sulle prestazioni del motore delle espressioni regolari, soprattutto se l'espressione regolare è progettata per elaborare un input non vincolato.</span><span class="sxs-lookup"><span data-stu-id="93303-146">When developing a pattern, you should consider how backtracking might affect the performance of the regular expression engine, particularly if your regular expression is designed to process unconstrained input.</span></span> <span data-ttu-id="93303-147">Per altre informazioni, vedere la sezione [Assumere il controllo del backtracking](#take-charge-of-backtracking).</span><span class="sxs-lookup"><span data-stu-id="93303-147">For more information, see the [Take charge of backtracking](#take-charge-of-backtracking) section.</span></span>

* <span data-ttu-id="93303-148">Testare in modo approfondito l'espressione regolare utilizzando un input non valido e quasi valido nonché un input valido.</span><span class="sxs-lookup"><span data-stu-id="93303-148">Thoroughly test your regular expression using invalid and near-valid input as well as valid input.</span></span> <span data-ttu-id="93303-149">Per generare casualmente input per un'espressione regolare specifica, è possibile usare [Rex](http://research.microsoft.com/en-us/projects/rex/), uno strumento di analisi delle espressioni regolari di Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="93303-149">To generate input for a particular regular expression randomly, you can use [Rex](http://research.microsoft.com/en-us/projects/rex/), which is a regular expression exploration tool from Microsoft Research.</span></span>

## <a name="handle-object-instantiation-appropriately"></a><span data-ttu-id="93303-150">Gestire la creazione di istanze degli oggetti in modo appropriato</span><span class="sxs-lookup"><span data-stu-id="93303-150">Handle object instantiation appropriately</span></span>

<span data-ttu-id="93303-151">Il modello a oggetti delle espressioni regolari di .NET è basato sulla classe [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex), che rappresenta il motore delle espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="93303-151">At the heart of .NET’s regular expression object model is the [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex) class, which represents the regular expression engine.</span></span> <span data-ttu-id="93303-152">Il fattore principale che spesso influisce sulle prestazioni delle espressioni regolari è il modo in cui viene usato il motore [Regex](xref:System.Text.RegularExpressions.Regex).</span><span class="sxs-lookup"><span data-stu-id="93303-152">Often, the single greatest factor that affects regular expression performance is the way in which the [Regex](xref:System.Text.RegularExpressions.Regex) engine is used.</span></span> <span data-ttu-id="93303-153">Per definire un'espressione regolare è necessario associare il motore delle espressioni regolari a un modello di espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="93303-153">Defining a regular expression involves tightly coupling the regular expression engine with a regular expression pattern.</span></span> <span data-ttu-id="93303-154">Tale processo di associazione, indipendentemente dal fatto che comporti la creazione di un'istanza di un oggetto [Regex](xref:System.Text.RegularExpressions.Regex) passando al relativo costruttore un modello di espressione regolare o la chiamata a un metodo statico passando il modello di espressione regolare con una stringa da analizzare, è necessariamente dispendioso.</span><span class="sxs-lookup"><span data-stu-id="93303-154">That coupling process, whether it involves instantiating a [Regex](xref:System.Text.RegularExpressions.Regex) object by passing its constructor a regular expression pattern or calling a static method by passing it the regular expression pattern along with the string to be analyzed, is by necessity an expensive one.</span></span>

<span data-ttu-id="93303-155">È possibile associare il motore delle espressioni regolari a un modello di espressione regolare specifico e quindi usare il motore per trovare una corrispondenza con il testo in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="93303-155">You can couple the regular expression engine with a particular regular expression pattern and then use the engine to match text in several ways:</span></span>

* <span data-ttu-id="93303-156">È possibile chiamare un metodo di corrispondenza dei modelli statico, ad esempio [Regex.Match(String, String)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String)).</span><span class="sxs-lookup"><span data-stu-id="93303-156">You can call a static pattern-matching method, such as [Regex.Match(String, String)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String)).</span></span> <span data-ttu-id="93303-157">Non è richiesta la creazione di un'istanza di un oggetto di espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="93303-157">This does not require instantiation of a regular expression object.</span></span>

* <span data-ttu-id="93303-158">È possibile creare un'istanza di un oggetto [Regex](xref:System.Text.RegularExpressions.Regex) e chiamare un metodo di corrispondenza dei modelli dell'istanza di un'espressione regolare interpretata.</span><span class="sxs-lookup"><span data-stu-id="93303-158">You can instantiate a [Regex](xref:System.Text.RegularExpressions.Regex) object and call an instance pattern-matching method of an interpreted regular expression.</span></span> <span data-ttu-id="93303-159">È il metodo predefinito per associare il motore delle espressioni regolari a un modello di espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="93303-159">This is the default method for binding the regular expression engine to a regular expression pattern.</span></span> <span data-ttu-id="93303-160">Si verifica quando viene creata un'istanza di un oggetto [Regex](xref:System.Text.RegularExpressions.Regex) senza un argomento options che include il flag [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled).</span><span class="sxs-lookup"><span data-stu-id="93303-160">It results when a [Regex](xref:System.Text.RegularExpressions.Regex) object is instantiated without an options argument that includes the [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) flag.</span></span>

* <span data-ttu-id="93303-161">È possibile creare un'istanza di un oggetto [Regex](xref:System.Text.RegularExpressions.Regex) e chiamare un metodo di corrispondenza dei modelli dell'istanza di un'espressione regolare compilata.</span><span class="sxs-lookup"><span data-stu-id="93303-161">You can instantiate a [Regex](xref:System.Text.RegularExpressions.Regex) object and call an instance pattern-matching method of a compiled regular expression.</span></span> <span data-ttu-id="93303-162">Gli oggetti di espressioni regolari rappresentano i modelli compilati quando l'istanza di un oggetto [Regex](xref:System.Text.RegularExpressions.Regex) viene creata con un argomento options che include il flag [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled).</span><span class="sxs-lookup"><span data-stu-id="93303-162">Regular expression objects represent compiled patterns when a [Regex](xref:System.Text.RegularExpressions.Regex) object is instantiated with an options argument that includes the [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) flag.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="93303-163">Il formato della chiamata al metodo (statico, interpretato, compilato) influisce sulle prestazioni se la stessa espressione regolare viene utilizzata più volte nelle chiamate al metodo oppure se in un'applicazione vengono utilizzati spesso gli oggetti di espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="93303-163">The form of the method call (static, interpreted, compiled) affects performance if the same regular expression is used repeatedly in method calls, or if an application makes extensive use of regular expression objects.</span></span>
 
### <a name="static-regular-expressions"></a><span data-ttu-id="93303-164">Espressioni regolari statiche</span><span class="sxs-lookup"><span data-stu-id="93303-164">Static regular expressions</span></span>

<span data-ttu-id="93303-165">I metodi con espressioni regolari statiche sono consigliati come alternativa alla creazione ripetuta di un'istanza di un oggetto di espressione regolare con la stessa espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="93303-165">Static regular expression methods are recommended as an alternative to repeatedly instantiating a regular expression object with the same regular expression.</span></span> <span data-ttu-id="93303-166">A differenza dei modelli di espressione regolare usati dagli oggetti di espressione regolare, i codici operativi o il linguaggio MSIL (Microsoft Intermediate Language) compilato dei modelli usati nelle chiamate al metodo di istanza vengono memorizzati nella cache interna dal motore delle espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="93303-166">Unlike regular expression patterns used by regular expression objects, either the operation codes or the compiled Microsoft intermediate language (MSIL) from patterns used in instance method calls is cached internally by the regular expression engine.</span></span> 

<span data-ttu-id="93303-167">È possibile ad esempio chiamare un metodo per convalidare l'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="93303-167">For example, you might call a method to validate user input.</span></span> <span data-ttu-id="93303-168">In questo esempio, un metodo denominato `IsValidCurrency` controlla se l'utente ha immesso un simbolo di valuta seguito da almeno una cifra decimale.</span><span class="sxs-lookup"><span data-stu-id="93303-168">In this example, a method named `IsValidCurrency` checks whether the user has entered a currency symbol followed by at least one decimal digit.</span></span> <span data-ttu-id="93303-169">Nell'esempio seguente viene illustrata un'implementazione molto inefficiente del metodo `IsValidCurrency`.</span><span class="sxs-lookup"><span data-stu-id="93303-169">A very inefficient implementation of the `IsValidCurrency` method is shown in the following example.</span></span> <span data-ttu-id="93303-170">Si noti che ogni chiamata al metodo crea una nuova istanza dell'oggetto [Regex](xref:System.Text.RegularExpressions.Regex) con lo stesso modello.</span><span class="sxs-lookup"><span data-stu-id="93303-170">Note that each method call reinstantiates a [Regex](xref:System.Text.RegularExpressions.Regex) object with the same pattern.</span></span> <span data-ttu-id="93303-171">Di conseguenza, il modello di espressione regolare deve essere ricompilato ogni volta che viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="93303-171">This, in turn, means that the regular expression pattern must be recompiled each time the method is called.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class RegexLib
{
   public static bool IsValidCurrency(string currencyValue)
   {
      string pattern = @"\p{Sc}+\s*\d+";
      Regex currencyRegex = new Regex(pattern);
      return currencyRegex.IsMatch(currencyValue);
   }
}
```

```vb
Public Sub OKButton_Click(sender As Object, e As EventArgs) _ 
           Handles OKButton.Click

   If Not String.IsNullOrEmpty(sourceCurrency.Text) Then
      If RegexLib.IsValidCurrency(sourceCurrency.Text) Then
         PerformConversion()
      Else
         status.Text = "The source currency value is invalid."
      End If          
   End If
End Sub
```

<span data-ttu-id="93303-172">È consigliabile sostituire questo codice inefficiente con una chiamata al metodo statico [Regex.IsMatch(String, String)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String)).</span><span class="sxs-lookup"><span data-stu-id="93303-172">You should replace this inefficient code with a call to the static [Regex.IsMatch(String, String)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String)) method.</span></span> <span data-ttu-id="93303-173">In questo modo si evita di dover creare un'istanza di un oggetto [Regex](xref:System.Text.RegularExpressions.Regex) ogni volta che si vuole chiamare un metodo di corrispondenza dei modelli e si consente al motore delle espressioni regolari di recuperare una versione compilata dell'espressione regolare dalla cache.</span><span class="sxs-lookup"><span data-stu-id="93303-173">This eliminates the need to instantiate a [Regex](xref:System.Text.RegularExpressions.Regex) object each time you want to call a pattern-matching method, and enables the regular expression engine to retrieve a compiled version of the regular expression from its cache.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class RegexLib
{
   public static bool IsValidCurrency(string currencyValue)
   {
      string pattern = @"\p{Sc}+\s*\d+";
      return Regex.IsMatch(currencyValue, pattern); 
   }
}
```

```vb
Imports System.Text.RegularExpressions

Public Module RegexLib
   Public Function IsValidCurrency(currencyValue As String) As Boolean
      Dim pattern As String = "\p{Sc}+\s*\d+"
      Return Regex.IsMatch(currencyValue, pattern)
   End Function
End Module
```

<span data-ttu-id="93303-174">Per impostazione predefinita, nella cache vengono memorizzati gli ultimi 15 modelli di espressione regolare statica usati più di recente.</span><span class="sxs-lookup"><span data-stu-id="93303-174">By default, the last 15 most recently used static regular expression patterns are cached.</span></span> <span data-ttu-id="93303-175">Per le applicazioni che richiedono un numero maggiore di espressioni regolari statiche memorizzate nella cache, la dimensione della cache può essere modificata impostando la proprietà [Regex.CacheSize](xref:System.Text.RegularExpressions.Regex.CacheSize).</span><span class="sxs-lookup"><span data-stu-id="93303-175">For applications that require a larger number of cached static regular expressions, the size of the cache can be adjusted by setting the [Regex.CacheSize](xref:System.Text.RegularExpressions.Regex.CacheSize) property.</span></span>

<span data-ttu-id="93303-176">L'espressione regolare `\p{Sc}+\s*\d+` usata in questo esempio verifica che la stringa di input sia costituita da un simbolo di valuta e da almeno una cifra decimale.</span><span class="sxs-lookup"><span data-stu-id="93303-176">The regular expression `\p{Sc}+\s*\d+` that is used in this example verifies that the input string consists of a currency symbol and at least one decimal digit.</span></span> <span data-ttu-id="93303-177">Il modello viene definito come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="93303-177">The pattern is defined as shown in the following table.</span></span>

<span data-ttu-id="93303-178">Modello</span><span class="sxs-lookup"><span data-stu-id="93303-178">Pattern</span></span> | <span data-ttu-id="93303-179">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93303-179">Description</span></span>
------- | -----------
`\p{Sc}+` | <span data-ttu-id="93303-180">Trova la corrispondenza di uno o più caratteri nella categoria Unicode Symbol, Currency.</span><span class="sxs-lookup"><span data-stu-id="93303-180">Match one or more characters in the Unicode Symbol, Currency category.</span></span>
`\s*` | <span data-ttu-id="93303-181">Trovare la corrispondenza di zero o più spazi vuoti.</span><span class="sxs-lookup"><span data-stu-id="93303-181">Match zero or more white-space characters.</span></span>
`\d+` | <span data-ttu-id="93303-182">Trova la corrispondenza con una o più cifre decimali.</span><span class="sxs-lookup"><span data-stu-id="93303-182">Match one or more decimal digits.</span></span>
 
### <a name="interpreted-vs-compiled-regular-expressions"></a><span data-ttu-id="93303-183">Espressioni regolari interpretate ed espressioni regolari compilate</span><span class="sxs-lookup"><span data-stu-id="93303-183">Interpreted vs. compiled regular expressions</span></span>

<span data-ttu-id="93303-184">I modelli di espressione regolare che non sono associati al motore delle espressioni mediante l'opzione [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) vengono interpretati.</span><span class="sxs-lookup"><span data-stu-id="93303-184">Regular expression patterns that are not bound to the regular expression engine through the specification of the [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) option are interpreted.</span></span> <span data-ttu-id="93303-185">Quando viene creata un'istanza di un oggetto di espressione regolare, il motore delle espressioni regolari converte l'espressione regolare in un set di codici operativi.</span><span class="sxs-lookup"><span data-stu-id="93303-185">When a regular expression object is instantiated, the regular expression engine converts the regular expression to a set of operation codes.</span></span> <span data-ttu-id="93303-186">Quando viene chiamato un metodo di istanza, i codici operativi vengono convertiti in MSIL ed eseguiti dal compilatore JIT.</span><span class="sxs-lookup"><span data-stu-id="93303-186">When an instance method is called, the operation codes are converted to MSIL and executed by the JIT compiler.</span></span> <span data-ttu-id="93303-187">Analogamente, quando viene chiamato un metodo con espressioni regolari statiche e l'espressione regolare non è presente nella cache, il motore delle espressioni regolari converte l'espressione regolare in un set di codici operativi che memorizza nella cache.</span><span class="sxs-lookup"><span data-stu-id="93303-187">Similarly, when a static regular expression method is called and the regular expression cannot be found in the cache, the regular expression engine converts the regular expression to a set of operation codes and stores them in the cache.</span></span> <span data-ttu-id="93303-188">Converte quindi i codici operativi in MSIL in modo tale che possano essere eseguiti dal compilatore JIT.</span><span class="sxs-lookup"><span data-stu-id="93303-188">It then converts these operation codes to MSIL so that the JIT compiler can execute them.</span></span> <span data-ttu-id="93303-189">Le espressioni regolari interpretate consentono di ridurre il tempo di avvio ma implicano tempi di esecuzione più lenti.</span><span class="sxs-lookup"><span data-stu-id="93303-189">Interpreted regular expressions reduce startup time at the cost of slower execution time.</span></span> <span data-ttu-id="93303-190">Per questo motivo, risultano particolarmente adatte quando l'espressione regolare viene utilizzata in un numero limitato di chiamate al metodo o se il numero esatto di chiamate ai metodi delle espressioni regolari è sconosciuto ma si prevede che sia esiguo.</span><span class="sxs-lookup"><span data-stu-id="93303-190">Because of this, they are best used when the regular expression is used in a small number of method calls, or if the exact number of calls to regular expression methods is unknown but is expected to be small.</span></span> <span data-ttu-id="93303-191">Man mano che aumenta il numero di chiamate al metodo, il miglioramento delle prestazioni rispetto alla riduzione del tempo di avvio viene superato dalla minore velocità di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="93303-191">As the number of method calls increases, the performance gain from reduced startup time is outstripped by the slower execution speed.</span></span>

<span data-ttu-id="93303-192">I modelli di espressione regolare che sono associati al motore delle espressioni mediante l'opzione [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) vengono compilati.</span><span class="sxs-lookup"><span data-stu-id="93303-192">Regular expression patterns that are bound to the regular expression engine through the specification of the [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) option are compiled.</span></span> <span data-ttu-id="93303-193">Ciò significa che quando viene creata un'istanza di un oggetto di espressione regolare o quando viene chiamato un metodo con espressioni regolari statiche e l'espressione regolare non è presente nella cache, il motore delle espressioni regolari converte l'espressione regolare in un set intermedio di codici operativi, il quale viene quindi convertito in MSIL.</span><span class="sxs-lookup"><span data-stu-id="93303-193">This means that, when a regular expression object is instantiated, or when a static regular expression method is called and the regular expression cannot be found in the cache, the regular expression engine converts the regular expression to an intermediary set of operation codes, which it then converts to MSIL.</span></span> <span data-ttu-id="93303-194">Il codice MSIL viene eseguito dal compilatore JIT non appena viene chiamato un metodo.</span><span class="sxs-lookup"><span data-stu-id="93303-194">When a method is called, the JIT compiler executes the MSIL.</span></span> <span data-ttu-id="93303-195">A differenza delle espressioni regolari interpretate, le espressioni regolari compilate aumentano il tempo di avvio eseguendo i singoli metodi di corrispondenza dei modelli più velocemente.</span><span class="sxs-lookup"><span data-stu-id="93303-195">In contrast to interpreted regular expressions, compiled regular expressions increase startup time but execute individual pattern-matching methods faster.</span></span> <span data-ttu-id="93303-196">Di conseguenza, il vantaggio in termini di prestazioni che risulta dalla compilazione dell'espressione regolare aumenta proporzionalmente al numero di metodi dell'espressione regolare chiamati.</span><span class="sxs-lookup"><span data-stu-id="93303-196">As a result, the performance benefit that results from compiling the regular expression increases in proportion to the number of regular expression methods called.</span></span>

<span data-ttu-id="93303-197">Riepilogando, è consigliabile utilizzare le espressioni regolari interpretate quando i metodi dell'espressione regolare vengono chiamati raramente con un'espressione regolare specifica</span><span class="sxs-lookup"><span data-stu-id="93303-197">To summarize, we recommend that you use interpreted regular expressions when you call regular expression methods with a specific regular expression relatively infrequently.</span></span> <span data-ttu-id="93303-198">e le espressioni regolari compilate quando i metodi dell'espressione regolare vengono chiamati frequentemente con un'espressione regolare specifica.</span><span class="sxs-lookup"><span data-stu-id="93303-198">You should use compiled regular expressions when you call regular expression methods with a specific regular expression relatively frequently.</span></span> <span data-ttu-id="93303-199">È difficile determinare la soglia esatta oltre la quale la minore velocità di esecuzione delle espressioni regolari interpretate supera i vantaggi offerti dalla riduzione del tempo di avvio o la soglia oltre la quale la riduzione del tempo di avvio delle espressioni regolari compilate supera i vantaggi offerti dalla maggiore velocità di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="93303-199">The exact threshold at which the slower execution speeds of interpreted regular expressions outweigh gains from their reduced startup time, or the threshold at which the slower startup times of compiled regular expressions outweigh gains from their faster execution speeds, is difficult to determine.</span></span> <span data-ttu-id="93303-200">Dipende da vari fattori, tra cui la complessità dell'espressione regolare e i dati specifici che vengono elaborati.</span><span class="sxs-lookup"><span data-stu-id="93303-200">It depends on a variety of factors, including the complexity of the regular expression and the specific data that it processes.</span></span> <span data-ttu-id="93303-201">Per determinare se le espressioni regolari interpretate o compilate offrono le migliori prestazioni per lo scenario specifico dell'applicazione, è possibile usare la classe [Stopwatch](xref:System.Diagnostics.Stopwatch) per confrontare i rispettivi tempi di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="93303-201">To determine whether interpreted or compiled regular expressions offer the best performance for your particular application scenario, you can use the [Stopwatch](xref:System.Diagnostics.Stopwatch) class to compare their execution times.</span></span>

<span data-ttu-id="93303-202">Nell'esempio seguente vengono confrontate le prestazioni delle espressioni regolari compilate e interpretate durante la lettura delle prime dieci frasi e durante la lettura di tutte le frasi del testo di The Financier di Theodore Dreiser.</span><span class="sxs-lookup"><span data-stu-id="93303-202">The following example compares the performance of compiled and interpreted regular expressions when reading the first ten sentences and when reading all the sentences in the text of Theodore Dreiser's The Financier.</span></span> <span data-ttu-id="93303-203">Come illustrato nell'output dell'esempio, quando vengono effettuate solo dieci chiamate ai metodi di corrispondenza delle espressioni regolari, un'espressione regolare interpretata offre prestazioni migliori rispetto a un'espressione regolare compilata.</span><span class="sxs-lookup"><span data-stu-id="93303-203">As the output from the example shows, when only ten calls are made to regular expression matching methods, an interpreted regular expression offers better performance than a compiled regular expression.</span></span> <span data-ttu-id="93303-204">Tuttavia, un'espressione regolare compilata offre prestazioni migliori quando viene effettuato un numero di chiamate maggiore, in questo caso oltre 13.000.</span><span class="sxs-lookup"><span data-stu-id="93303-204">However, a compiled regular expression offers better performance when a large number of calls (in this case, over 13,000) are made.</span></span> 

```csharp
using System;
using System.Diagnostics;
using System.IO;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]";
      Stopwatch sw;
      Match match;
      int ctr;

      StreamReader inFile = new StreamReader(@".\Dreiser_TheFinancier.txt");
      string input = inFile.ReadToEnd();
      inFile.Close();

      // Read first ten sentences with interpreted regex.
      Console.WriteLine("10 Sentences with Interpreted Regex:");
      sw = Stopwatch.StartNew();
      Regex int10 = new Regex(pattern, RegexOptions.Singleline);
      match = int10.Match(input);
      for (ctr = 0; ctr <= 9; ctr++) {
         if (match.Success)
            // Do nothing with the match except get the next match.
            match = match.NextMatch();
         else
            break;
      }
      sw.Stop();
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed);

      // Read first ten sentences with compiled regex.
      Console.WriteLine("10 Sentences with Compiled Regex:");
      sw = Stopwatch.StartNew();
      Regex comp10 = new Regex(pattern, 
                   RegexOptions.Singleline | RegexOptions.Compiled);
      match = comp10.Match(input);
      for (ctr = 0; ctr <= 9; ctr++) {
         if (match.Success)
            // Do nothing with the match except get the next match.
            match = match.NextMatch();
         else
            break;
      }
      sw.Stop();
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed);

      // Read all sentences with interpreted regex.
      Console.WriteLine("All Sentences with Interpreted Regex:");
      sw = Stopwatch.StartNew();
      Regex intAll = new Regex(pattern, RegexOptions.Singleline);
      match = intAll.Match(input);
      int matches = 0;
      while (match.Success) {
         matches++;
         // Do nothing with the match except get the next match.
         match = match.NextMatch();
      }
      sw.Stop();
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed);

      // Read all sentnces with compiled regex.
      Console.WriteLine("All Sentences with Compiled Regex:");
      sw = Stopwatch.StartNew();
      Regex compAll = new Regex(pattern, 
                      RegexOptions.Singleline | RegexOptions.Compiled);
      match = compAll.Match(input);
      matches = 0;
      while (match.Success) {
         matches++;
         // Do nothing with the match except get the next match.
         match = match.NextMatch();
      }
      sw.Stop();
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed);      
   }
}
// The example displays the following output:
//       10 Sentences with Interpreted Regex:
//          10 matches in 00:00:00.0047491
//       10 Sentences with Compiled Regex:
//          10 matches in 00:00:00.0141872
//       All Sentences with Interpreted Regex:
//          13,443 matches in 00:00:01.1929928
//       All Sentences with Compiled Regex:
//          13,443 matches in 00:00:00.7635869
//       
//       >compare1
//       10 Sentences with Interpreted Regex:
//          10 matches in 00:00:00.0046914
//       10 Sentences with Compiled Regex:
//          10 matches in 00:00:00.0143727
//       All Sentences with Interpreted Regex:
//          13,443 matches in 00:00:01.1514100
//       All Sentences with Compiled Regex:
//          13,443 matches in 00:00:00.7432921
```

```vb
Imports System.Diagnostics
Imports System.IO
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]"
      Dim sw As Stopwatch
      Dim match As Match
      Dim ctr As Integer

      Dim inFile As New StreamReader(".\Dreiser_TheFinancier.txt")
      Dim input As String = inFile.ReadToEnd()
      inFile.Close()

      ' Read first ten sentences with interpreted regex.
      Console.WriteLine("10 Sentences with Interpreted Regex:")
      sw = Stopwatch.StartNew()
      Dim int10 As New Regex(pattern, RegexOptions.SingleLine)
      match = int10.Match(input)
      For ctr = 0 To 9
         If match.Success Then
            ' Do nothing with the match except get the next match.
            match = match.NextMatch()
         Else
            Exit For
         End If
      Next
      sw.Stop()
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed)

      ' Read first ten sentences with compiled regex.
      Console.WriteLine("10 Sentences with Compiled Regex:")
      sw = Stopwatch.StartNew()
      Dim comp10 As New Regex(pattern, 
                   RegexOptions.SingleLine Or RegexOptions.Compiled)
      match = comp10.Match(input)
      For ctr = 0 To 9
         If match.Success Then
            ' Do nothing with the match except get the next match.
            match = match.NextMatch()
         Else
            Exit For
         End If
      Next
      sw.Stop()
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed)

      ' Read all sentences with interpreted regex.
      Console.WriteLine("All Sentences with Interpreted Regex:")
      sw = Stopwatch.StartNew()
      Dim intAll As New Regex(pattern, RegexOptions.SingleLine)
      match = intAll.Match(input)
      Dim matches As Integer = 0
      Do While match.Success
         matches += 1
         ' Do nothing with the match except get the next match.
         match = match.NextMatch()
      Loop
      sw.Stop()
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed)

      ' Read all sentnces with compiled regex.
      Console.WriteLine("All Sentences with Compiled Regex:")
      sw = Stopwatch.StartNew()
      Dim compAll As New Regex(pattern, 
                     RegexOptions.SingleLine Or RegexOptions.Compiled)
      match = compAll.Match(input)
      matches = 0
      Do While match.Success
         matches += 1
         ' Do nothing with the match except get the next match.
         match = match.NextMatch()
      Loop
      sw.Stop()
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed)      
   End Sub
End Module
' The example displays output like the following:
'       10 Sentences with Interpreted Regex:
'          10 matches in 00:00:00.0047491
'       10 Sentences with Compiled Regex:
'          10 matches in 00:00:00.0141872
'       All Sentences with Interpreted Regex:
'          13,443 matches in 00:00:01.1929928
'       All Sentences with Compiled Regex:
'          13,443 matches in 00:00:00.7635869
'       
'       >compare1
'       10 Sentences with Interpreted Regex:
'          10 matches in 00:00:00.0046914
'       10 Sentences with Compiled Regex:
'          10 matches in 00:00:00.0143727
'       All Sentences with Interpreted Regex:
'          13,443 matches in 00:00:01.1514100
'       All Sentences with Compiled Regex:
'          13,443 matches in 00:00:00.7432921
```

<span data-ttu-id="93303-205">Il criterio di espressione regolare usato nell'esempio, `\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]`, è definito nel modo illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="93303-205">The regular expression pattern used in the example, `\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]`, is defined as shown in the following table.</span></span>

<span data-ttu-id="93303-206">Modello</span><span class="sxs-lookup"><span data-stu-id="93303-206">Pattern</span></span> | <span data-ttu-id="93303-207">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93303-207">Description</span></span>
------- | -----------
`\b` | <span data-ttu-id="93303-208">Inizia la corrispondenza sul confine di parola.</span><span class="sxs-lookup"><span data-stu-id="93303-208">Begin the match at a word boundary.</span></span>
`\w+` | <span data-ttu-id="93303-209">Trova la corrispondenza di uno o più caratteri alfanumerici.</span><span class="sxs-lookup"><span data-stu-id="93303-209">Match one or more word characters.</span></span>
<span data-ttu-id="93303-210">\`(\r?\n)</span><span class="sxs-lookup"><span data-stu-id="93303-210">\`(\r?\n)</span></span>|<span data-ttu-id="93303-211">,?\s)\`</span><span class="sxs-lookup"><span data-stu-id="93303-211">,?\s)\`</span></span> | <span data-ttu-id="93303-212">Trova la corrispondenza di uno o nessun ritorno a capo seguito da un carattere di nuova riga o di una o nessuna virgola seguita da uno spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="93303-212">Match either zero or one carriage return followed by a newline character, or zero or one comma followed by a white-space character.</span></span>
<span data-ttu-id="93303-213">\`(\w+((\r?\n)</span><span class="sxs-lookup"><span data-stu-id="93303-213">\`(\w+((\r?\n)</span></span>|<span data-ttu-id="93303-214">,?\s))*\`</span><span class="sxs-lookup"><span data-stu-id="93303-214">,?\s))*\`</span></span> | <span data-ttu-id="93303-215">Trova la corrispondenza di zero o più occorrenze di uno o più caratteri alfanumerici seguiti da uno o nessun ritorno a capo e un carattere di nuova riga o da una o nessuna virgola seguita da uno spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="93303-215">Match zero or more occurrences of one or more word characters that are followed either by zero or one carriage return and a newline character, or by zero or one comma followed by a white-space character.</span></span>
`\w+` | <span data-ttu-id="93303-216">Trova la corrispondenza di uno o più caratteri alfanumerici.</span><span class="sxs-lookup"><span data-stu-id="93303-216">Match one or more word characters.</span></span>
`[.?:;!]` | <span data-ttu-id="93303-217">Trova la corrispondenza di un punto, un punto interrogativo, due punti, un punto e virgola o un punto esclamativo.</span><span class="sxs-lookup"><span data-stu-id="93303-217">Match a period, question mark, colon, semicolon, or exclamation point.</span></span>
 
## <a name="take-charge-of-backtracking"></a><span data-ttu-id="93303-218">Assumere il controllo del backtracking</span><span class="sxs-lookup"><span data-stu-id="93303-218">Take charge of backtracking</span></span>

<span data-ttu-id="93303-219">In genere, il motore delle espressioni regolari usa la progressione lineare per spostarsi in una stringa di input e confrontarla con un modello di espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="93303-219">Ordinarily, the regular expression engine uses linear progression to move through an input string and compare it to a regular expression pattern.</span></span> <span data-ttu-id="93303-220">Tuttavia, quando in un modello di espressione regolare vengono usati quantificatori indeterminati come __*__, **+** e **?**,</span><span class="sxs-lookup"><span data-stu-id="93303-220">However, when indeterminate quantifiers such as __*__, **+**, and **?**</span></span> <span data-ttu-id="93303-221">il motore delle espressioni regolari può tralasciare una parte delle corrispondenze parziali corrette e tornare a uno stato salvato in precedenza per cercare una corrispondenza corretta per l'intero modello.</span><span class="sxs-lookup"><span data-stu-id="93303-221">are used in a regular expression pattern, the regular expression engine may give up a portion of successful partial matches and return to a previously saved state in order to search for a successful match for the entire pattern.</span></span> <span data-ttu-id="93303-222">Questo processo è noto come backtracking.</span><span class="sxs-lookup"><span data-stu-id="93303-222">This process is known as backtracking.</span></span>

> [!NOTE]
> <span data-ttu-id="93303-223">Per altre informazioni sul backtracking, vedere [Dettagli sul comportamento delle espressioni regolari](regex-behavior.md) e [Backtracking nelle espressioni regolari](backtracking.md).</span><span class="sxs-lookup"><span data-stu-id="93303-223">For more information on backtracking, see [Details of regular expression behavior](regex-behavior.md) and [Backtracking in regular expressions](backtracking.md).</span></span>
 
<span data-ttu-id="93303-224">Il supporto del backtracking fornisce alle espressioni regolari potenza e flessibilità.</span><span class="sxs-lookup"><span data-stu-id="93303-224">Support for backtracking gives regular expressions power and flexibility.</span></span> <span data-ttu-id="93303-225">Inoltre la responsabilità del controllo del funzionamento del motore delle espressioni regolari viene affidata agli sviluppatori delle espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="93303-225">It also places the responsibility for controlling the operation of the regular expression engine in the hands of regular expression developers.</span></span> <span data-ttu-id="93303-226">Poiché spesso gli sviluppatori non sono consapevoli di questa responsabilità, un utilizzo improprio del backtracking o un utilizzo eccessivo del backtracking rappresenta spesso la causa principale della riduzione delle prestazioni delle espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="93303-226">Because developers are often not aware of this responsibility, their misuse of backtracking or reliance on excessive backtracking often plays the most significant role in degrading regular expression performance.</span></span> <span data-ttu-id="93303-227">Nello scenario peggiore, il tempo di esecuzione può raddoppiarsi per ogni carattere aggiuntivo nella stringa di input.</span><span class="sxs-lookup"><span data-stu-id="93303-227">In a worst-case scenario, execution time can double for each additional character in the input string.</span></span> <span data-ttu-id="93303-228">Utilizzando infatti il backtracking in modo eccessivo, è facile creare l'equivalente a livello di codice di un ciclo infinito se l'input corrisponde quasi al modello di espressione regolare. Il motore delle espressioni regolari può richiedere ore o persino giorni per l'elaborazione di una stringa di input relativamente breve.</span><span class="sxs-lookup"><span data-stu-id="93303-228">In fact, by using backtracking excessively, it is easy to create the programmatic equivalent of an endless loop if input nearly matches the regular expression pattern; the regular expression engine may take hours or even days to process a relatively short input string.</span></span>

<span data-ttu-id="93303-229">L'utilizzo del backtracking comporta spesso una riduzione delle prestazioni delle applicazioni sebbene il backtracking non sia essenziale per una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="93303-229">Often, applications pay a performance penalty for using backtracking despite the fact that backtracking is not essential for a match.</span></span> <span data-ttu-id="93303-230">Ad esempio, l'espressione regolare `\b\p{Lu}\w*\b` cerca una corrispondenza di tutte le parole che iniziano con un carattere maiuscolo, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="93303-230">For example, the regular expression `\b\p{Lu}\w*\b` matches all words that begin with an uppercase character, as the following table shows.</span></span>

<span data-ttu-id="93303-231">Modello</span><span class="sxs-lookup"><span data-stu-id="93303-231">Pattern</span></span> | <span data-ttu-id="93303-232">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93303-232">Description</span></span>
------- | -----------
`\b` | <span data-ttu-id="93303-233">Inizia la corrispondenza sul confine di parola.</span><span class="sxs-lookup"><span data-stu-id="93303-233">Begin the match at a word boundary.</span></span>
`\p{Lu}` | <span data-ttu-id="93303-234">Trova la corrispondenza di un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="93303-234">Match an uppercase character.</span></span>
`\w*` | <span data-ttu-id="93303-235">Trova la corrispondenza di zero o più caratteri alfanumerici.</span><span class="sxs-lookup"><span data-stu-id="93303-235">Match zero or more word characters.</span></span>
`\b` | <span data-ttu-id="93303-236">Termina la corrispondenza sul confine di parola.</span><span class="sxs-lookup"><span data-stu-id="93303-236">End the match at a word boundary.</span></span>
 
<span data-ttu-id="93303-237">Poiché un confine di parola non è uguale a un carattere alfanumerico né è un subset di tali caratteri, non è possibile che il motore delle espressioni regolari attraversi un confine di parola quando viene trovata una corrispondenza con i caratteri alfanumerici.</span><span class="sxs-lookup"><span data-stu-id="93303-237">Because a word boundary is not the same as, or a subset of, a word character, there is no possibility that the regular expression engine will cross a word boundary when matching word characters.</span></span> <span data-ttu-id="93303-238">Ciò significa che per questa espressione regolare, il backtracking non potrà mai contribuire alla riuscita dell'operazione ma potrà solo ridurre le prestazioni poiché il motore delle espressioni regolari deve salvare lo stato per ogni corrispondenza preliminare corretta di un carattere alfanumerico.</span><span class="sxs-lookup"><span data-stu-id="93303-238">This means that for this regular expression, backtracking can never contribute to the overall success of any match -- it can only degrade performance, because the regular expression engine is forced to save its state for each successful preliminary match of a word character.</span></span>

<span data-ttu-id="93303-239">Se si determina che il backtracking non è necessario, è possibile disabilitarlo usando l'elemento del linguaggio **(?>**_subexpression_**)**.</span><span class="sxs-lookup"><span data-stu-id="93303-239">If you determine that backtracking is not necessary, you can disable it by using the **(?>**_subexpression_**)** language element.</span></span> <span data-ttu-id="93303-240">Nell'esempio seguente viene analizzata una stringa di input utilizzando due espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="93303-240">The following example parses an input string by using two regular expressions.</span></span> <span data-ttu-id="93303-241">La prima, `\b\p{Lu}\w*\b`, si basa sul backtracking.</span><span class="sxs-lookup"><span data-stu-id="93303-241">The first, `\b\p{Lu}\w*\b`, relies on backtracking.</span></span> <span data-ttu-id="93303-242">La seconda, `\b\p{Lu}(?>\w*)\b`, disabilita il backtracking.</span><span class="sxs-lookup"><span data-stu-id="93303-242">The second, `\b\p{Lu}(?>\w*)\b`, disables backtracking.</span></span> <span data-ttu-id="93303-243">Come illustrato nell'output dell'esempio, entrambe producono lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="93303-243">As the output from the example shows, they both produce the same result.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This this word Sentence name Capital";
      string pattern = @"\b\p{Lu}\w*\b";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);

      Console.WriteLine();

      pattern = @"\b\p{Lu}(?>\w*)\b";   
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       This
//       Sentence
//       Capital
//       
//       This
//       Sentence
//       Capital
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This this word Sentence name Capital"
      Dim pattern As String = "\b\p{Lu}\w*\b"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
      Next
      Console.WriteLine()

      pattern = "\b\p{Lu}(?>\w*)\b"   
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       This
'       Sentence
'       Capital
'       
'       This
'       Sentence
'       Capital
```

<span data-ttu-id="93303-244">In molti casi, il backtracking è essenziale per la corrispondenza di un modello di espressione regolare con il testo di input.</span><span class="sxs-lookup"><span data-stu-id="93303-244">In many cases, backtracking is essential for matching a regular expression pattern to input text.</span></span> <span data-ttu-id="93303-245">Tuttavia, un utilizzo eccessivo del backtracking può ridurre notevolmente le prestazioni e dare l'impressione che un'applicazione non risponda.</span><span class="sxs-lookup"><span data-stu-id="93303-245">However, excessive backtracking can severely degrade performance and create the impression that an application has stopped responding.</span></span> <span data-ttu-id="93303-246">In particolare, tale situazione si verifica quando vengono annidati i quantificatori e il testo che corrisponde alla sottoespressione esterna è un subset del testo che corrisponde alla sottoespressione interna.</span><span class="sxs-lookup"><span data-stu-id="93303-246">In particular, this happens when quantifiers are nested and the text that matches the outer subexpression is a subset of the text that matches the inner subexpression.</span></span> 

> [!WARNING]
> <span data-ttu-id="93303-247">Oltre a evitare un eccessivo utilizzo del backtracking, è necessario utilizzare la funzionalità di timeout per assicurarsi che l'eccessivo backtracking non comprometta troppo le prestazioni dell'espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="93303-247">In addition to avoiding excessive backtracking, you should use the timeout feature to ensure that excessive backtracking does not severely degrade regular expression performance.</span></span> <span data-ttu-id="93303-248">Per altre informazioni, vedere la sezione [Usare valori di timeout](#use-time-out-values).</span><span class="sxs-lookup"><span data-stu-id="93303-248">For more information, see the [Use time-out values](#use-time-out-values) section.</span></span>
 
<span data-ttu-id="93303-249">Ad esempio, il criterio di espressione regolare `^[0-9A-Z]([-.\w]*[0-9A-Z])*\$$` viene usato per trovare la corrispondenza con un numero parte costituito da almeno un carattere alfanumerico.</span><span class="sxs-lookup"><span data-stu-id="93303-249">For example, the regular expression pattern `^[0-9A-Z]([-.\w]*[0-9A-Z])*\$$` is intended to match a part number that consists of at least one alphanumeric character.</span></span> <span data-ttu-id="93303-250">Tutti i caratteri aggiuntivi possono essere costituiti da un carattere alfanumerico, un trattino, un carattere di sottolineatura o un punto, sebbene l'ultimo carattere debba essere alfanumerico.</span><span class="sxs-lookup"><span data-stu-id="93303-250">Any additional characters can consist of an alphanumeric character, a hyphen, an underscore, or a period, though the last character must be alphanumeric.</span></span> <span data-ttu-id="93303-251">Il numero parte termina con il simbolo del dollaro.</span><span class="sxs-lookup"><span data-stu-id="93303-251">A dollar sign terminates the part number.</span></span> <span data-ttu-id="93303-252">In alcuni casi, il criterio di espressione regolare può presentare prestazioni estremamente insufficienti perché vengono annidati i quantificatori e perché la sottoespressione `[0-9A-Z]` è un subset della sottoespressione `[-.\w]*`.</span><span class="sxs-lookup"><span data-stu-id="93303-252">In some cases, this regular expression pattern can exhibit extremely poor performance because quantifiers are nested, and because the subexpression `[0-9A-Z]` is a subset of the subexpression `[-.\w]*`.</span></span>

<span data-ttu-id="93303-253">In questi casi, è possibile ottimizzare le prestazioni dell'espressione regolare rimuovendo i quantificatori annidati e sostituendo la sottoespressione esterna con un'asserzione lookahead o lookbehind di larghezza zero.</span><span class="sxs-lookup"><span data-stu-id="93303-253">In these cases, you can optimize regular expression performance by removing the nested quantifiers and replacing the outer subexpression with a zero-width lookahead or lookbehind assertion.</span></span> <span data-ttu-id="93303-254">Le asserzioni lookahead e lookbehind sono ancoraggi; non spostano il puntatore nella stringa di input, ma eseguono il lookahead e lookbehind per verificare se è stata soddisfatta una condizione specificata.</span><span class="sxs-lookup"><span data-stu-id="93303-254">Lookahead and lookbehind assertions are anchors; they do not move the pointer in the input string, but instead look ahead or behind to check whether a specified condition is met.</span></span> <span data-ttu-id="93303-255">Ad esempio, l'espressione regolare del numero parte può essere riscritta come `^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$`.</span><span class="sxs-lookup"><span data-stu-id="93303-255">For example, the part number regular expression can be rewritten as `^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$`.</span></span> <span data-ttu-id="93303-256">Tale modello di espressione regolare viene definito come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="93303-256">This regular expression pattern is defined as shown in the following table.</span></span>

<span data-ttu-id="93303-257">Modello</span><span class="sxs-lookup"><span data-stu-id="93303-257">Pattern</span></span> | <span data-ttu-id="93303-258">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93303-258">Description</span></span>
------- | -----------
`^` | <span data-ttu-id="93303-259">Inizia la corrispondenza all'inizio della stringa di input.</span><span class="sxs-lookup"><span data-stu-id="93303-259">Begin the match at the beginning of the input string.</span></span>
`[0-9A-Z]` | <span data-ttu-id="93303-260">Trova la corrispondenza di un carattere alfanumerico.</span><span class="sxs-lookup"><span data-stu-id="93303-260">Match an alphanumeric character.</span></span> <span data-ttu-id="93303-261">Il numero parte deve essere costituito da almeno uno di questi caratteri.</span><span class="sxs-lookup"><span data-stu-id="93303-261">The part number must consist of at least this character.</span></span>
`[-.\w]*` | <span data-ttu-id="93303-262">Trova la corrispondenza di zero o più occorrenze di un carattere alfanumerico, un trattino o un punto.</span><span class="sxs-lookup"><span data-stu-id="93303-262">Match zero or more occurrences of any word character, hyphen, or period.</span></span>
<span data-ttu-id="93303-263">\`\$]</span><span class="sxs-lookup"><span data-stu-id="93303-263">\`\$]</span></span> | <span data-ttu-id="93303-264">Trova la corrispondenza di un simbolo del dollaro.</span><span class="sxs-lookup"><span data-stu-id="93303-264">Match a dollar sign.</span></span>
`(?<=[0-9A-Z])` | <span data-ttu-id="93303-265">Esegue il lookahead del simbolo del dollaro finale per verificare che il carattere precedente sia alfanumerico.</span><span class="sxs-lookup"><span data-stu-id="93303-265">Look ahead of the ending dollar sign to ensure that the previous character is alphanumeric.</span></span>
<span data-ttu-id="93303-266">`$` Termina la ricerca della corrispondenza alla fine della stringa di input.</span><span class="sxs-lookup"><span data-stu-id="93303-266">`$` End the match at the end of the input string.</span></span>
 
<span data-ttu-id="93303-267">Nell'esempio seguente viene illustrato l'utilizzo dell'espressione regolare per trovare la corrispondenza con una matrice contenente i numeri parte possibili.</span><span class="sxs-lookup"><span data-stu-id="93303-267">The following example illustrates the use of this regular expression to match an array containing possible part numbers.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$";
      string[] partNos = { "A1C$", "A4", "A4$", "A1603D$", "A1603D#" };

      foreach (var input in partNos) {
         Match match = Regex.Match(input, pattern);
         if (match.Success)
            Console.WriteLine(match.Value);
         else
            Console.WriteLine("Match not found.");
      }      
   }
}
// The example displays the following output:
//       A1C$
//       Match not found.
//       A4$
//       A1603D$
//       Match not found.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$"
      Dim partNos() As String = { "A1C$", "A4", "A4$", "A1603D$", 
                                  "A1603D#" }

      For Each input As String In partNos
         Dim match As Match = Regex.Match(input, pattern)
         If match.Success Then
            Console.WriteLine(match.Value)
         Else
            Console.WriteLine("Match not found.")
         End If
      Next      
   End Sub
End Module
' The example displays the following output:
'       A1C$
'       Match not found.
'       A4$
'       A1603D$
'       Match not found.
```

<span data-ttu-id="93303-268">Il linguaggio delle espressioni regolari in .NET include i seguenti elementi che è possibile usare per eliminare i quantificatori annidati.</span><span class="sxs-lookup"><span data-stu-id="93303-268">The regular expression language in .NET includes the following language elements that you can use to eliminate nested quantifiers.</span></span> <span data-ttu-id="93303-269">Per altre informazioni, vedere [Costrutti di raggruppamento nelle espressioni regolari](grouping.md).</span><span class="sxs-lookup"><span data-stu-id="93303-269">For more information, see [Grouping constructs in regular expressions](grouping.md).</span></span>

<span data-ttu-id="93303-270">Elemento di linguaggio</span><span class="sxs-lookup"><span data-stu-id="93303-270">Language element</span></span> | <span data-ttu-id="93303-271">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93303-271">Description</span></span>
---------------- | ----------- 
<span data-ttu-id="93303-272">**(?**=_subexpression_**)**</span><span class="sxs-lookup"><span data-stu-id="93303-272">**(?**=_subexpression_**)**</span></span> | <span data-ttu-id="93303-273">Asserzione lookahead positiva di larghezza zero.</span><span class="sxs-lookup"><span data-stu-id="93303-273">Zero-width positive lookahead.</span></span> <span data-ttu-id="93303-274">Lookahead della posizione corrente per determinare se *subexpression* corrisponde alla stringa di input.</span><span class="sxs-lookup"><span data-stu-id="93303-274">Look ahead of the current position to determine whether *subexpression* matches the input string.</span></span>
<span data-ttu-id="93303-275">**(?!**_subexpression_**)**</span><span class="sxs-lookup"><span data-stu-id="93303-275">**(?!**_subexpression_**)**</span></span> | <span data-ttu-id="93303-276">Asserzione lookahead negativa di larghezza zero.</span><span class="sxs-lookup"><span data-stu-id="93303-276">Zero-width negative lookahead.</span></span> <span data-ttu-id="93303-277">Lookahead della posizione corrente per determinare se *subexpression* non corrisponde alla stringa di input.</span><span class="sxs-lookup"><span data-stu-id="93303-277">Look ahead of the current position to determine whether *subexpression* does not match the input string.</span></span>
<span data-ttu-id="93303-278">**(?<**=_subexpression_**)**</span><span class="sxs-lookup"><span data-stu-id="93303-278">**(?<**=_subexpression_**)**</span></span> | <span data-ttu-id="93303-279">Lookbehind positivo di larghezza zero.</span><span class="sxs-lookup"><span data-stu-id="93303-279">Zero-width positive lookbehind.</span></span> <span data-ttu-id="93303-280">Lookbehind della posizione corrente per determinare se *subexpression* corrisponde alla stringa di input.</span><span class="sxs-lookup"><span data-stu-id="93303-280">Look behind the current position to determine whether *subexpression* matches the input string.</span></span>
<span data-ttu-id="93303-281">**(?<!**_subexpression_**)**</span><span class="sxs-lookup"><span data-stu-id="93303-281">**(?<!**_subexpression_**)**</span></span> | <span data-ttu-id="93303-282">Lookbehind negativo di larghezza zero.</span><span class="sxs-lookup"><span data-stu-id="93303-282">Zero-width negative lookbehind.</span></span> <span data-ttu-id="93303-283">Lookbehind della posizione corrente per determinare se *subexpression* non corrisponde alla stringa di input.</span><span class="sxs-lookup"><span data-stu-id="93303-283">Look behind the current position to determine whether *subexpression* does not match the input string.</span></span>
 
## <a name="use-time-out-values"></a><span data-ttu-id="93303-284">Usare valori di timeout</span><span class="sxs-lookup"><span data-stu-id="93303-284">Use time-out values</span></span>

<span data-ttu-id="93303-285">Se le espressioni regolari elaborano l'input che corrisponde quasi al modello dell'espressione regolare, possono spesso basarsi su un backtracking eccessivo, con un impatto notevole sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="93303-285">If your regular expressions processes input that nearly matches the regular expression pattern, it can often rely on excessive backtracking, which impacts its performance significantly.</span></span> <span data-ttu-id="93303-286">Oltre a considerare attentamente l'utilizzo del backtracking e a testare l'espressione regolare rispetto all'input maggiormente corrispondente, è necessario impostare sempre un valore di timeout per assicurarsi che l'impatto di un eventuale backtracking eccessivo sia contenuto.</span><span class="sxs-lookup"><span data-stu-id="93303-286">In addition to carefully considering your use of backtracking and testing the regular expression against near-matching input, you should always set a time-out value to ensure that the impact of excessive backtracking, if it occurs, is minimized.</span></span>

<span data-ttu-id="93303-287">L'intervallo di timeout dell'espressione regolare definisce il periodo di tempo durante il quale il motore delle espressioni regolari cercherà una singola corrispondenza prima del timeout.</span><span class="sxs-lookup"><span data-stu-id="93303-287">The regular expression time-out interval defines the period of time that the regular expression engine will look for a single match before it times out.</span></span> <span data-ttu-id="93303-288">L'intervallo di timeout predefinito è [Regex.InfiniteMatchTimeout](xref:System.Text.RegularExpressions.Regex.InfiniteMatchTimeout) che significa che l'espressione regolare non scadrà.</span><span class="sxs-lookup"><span data-stu-id="93303-288">The default time-out interval is [Regex.InfiniteMatchTimeout](xref:System.Text.RegularExpressions.Regex.InfiniteMatchTimeout), which means that the regular expression will not time out.</span></span> <span data-ttu-id="93303-289">È possibile eseguire l'override di questo valore e definire un intervallo di timeout come segue:</span><span class="sxs-lookup"><span data-stu-id="93303-289">You can override this value and define a time-out interval as follows:</span></span> 

* <span data-ttu-id="93303-290">Specificando un valore di timeout quando si crea un'istanza di un oggetto [Regex](xref:System.Text.RegularExpressions.Regex) chiamando il costruttore [Regex(String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.%23ctor(System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)).</span><span class="sxs-lookup"><span data-stu-id="93303-290">By providing a time-out value when you instantiate a [Regex](xref:System.Text.RegularExpressions.Regex) object by calling the [Regex(String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.%23ctor(System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)) constructor.</span></span>

* <span data-ttu-id="93303-291">Chiamando un metodo di corrispondenza statico, ad esempio [Regex.Match(String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)) o [Regex.Replace(String, String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)) che include un parametro *matchTimeout*.</span><span class="sxs-lookup"><span data-stu-id="93303-291">By calling a static pattern matching method, such as [Regex.Match(String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)) or [Regex.Replace(String, String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)), that includes a *matchTimeout* parameter.</span></span>

<span data-ttu-id="93303-292">Se è stato definito un intervallo di timeout e non viene trovata alcuna corrispondenza alla fine di questo intervallo, il metodo dell'espressione regolare genera un'eccezione [RegexMatchTimeoutException](xref:System.Text.RegularExpressions.RegexMatchTimeoutException).</span><span class="sxs-lookup"><span data-stu-id="93303-292">If you have defined a time-out interval and a match is not found at the end of that interval, the regular expression method throws a [RegexMatchTimeoutException](xref:System.Text.RegularExpressions.RegexMatchTimeoutException) exception.</span></span> <span data-ttu-id="93303-293">Nel gestore eccezioni, è possibile continuare a cercare la corrispondenza con un intervallo di timeout più lungo, abbandonare il tentativo di ricerca supponendo che non esista alcuna corrispondenza oppure abbandonare il tentativo di ricerca e registrare le informazioni sull'eccezione per un'analisi futura.</span><span class="sxs-lookup"><span data-stu-id="93303-293">In your exception handler, you can choose to retry the match with a longer time-out interval, abandon the match attempt and assume that there is no match, or abandon the match attempt and log the exception information for future analysis.</span></span>

<span data-ttu-id="93303-294">Nell'esempio seguente viene definito un metodo `GetWordData` che crea un'istanza di un'espressione regolare con un intervallo di timeout di 350 millisecondi per calcolare il numero di parole e il numero medio di caratteri di una parola in un documento di testo.</span><span class="sxs-lookup"><span data-stu-id="93303-294">The following example defines a `GetWordData` method that instantiates a regular expression with a time-out interval of 350 milliseconds to calculate the number of words and average number of characters in a word in a text document.</span></span> <span data-ttu-id="93303-295">Se l'operazione di ricerca della corrispondenza scade, l'intervallo di timeout viene aumentato di 350 millisecondi e viene nuovamente creata un'istanza dell'oggetto [Regex](xref:System.Text.RegularExpressions.Regex).</span><span class="sxs-lookup"><span data-stu-id="93303-295">If the matching operation times out, the time-out interval is increased by 350 milliseconds and the [Regex](xref:System.Text.RegularExpressions.Regex) object is re-instantiated.</span></span> <span data-ttu-id="93303-296">Se il nuovo intervallo di timeout supera 1 secondo, il metodo genera nuovamente l'eccezione al chiamante.</span><span class="sxs-lookup"><span data-stu-id="93303-296">If the new time-out interval exceeds 1 second, the method re-throws the exception to the caller.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      RegexUtilities util = new RegexUtilities();
      string title = "Doyle - The Hound of the Baskervilles.txt";
      try {
         var info = util.GetWordData(title);
         Console.WriteLine("Words:               {0:N0}", info.Item1);
         Console.WriteLine("Average Word Length: {0:N2} characters", info.Item2); 
      }
      catch (IOException e) {
         Console.WriteLine("IOException reading file '{0}'", title);
         Console.WriteLine(e.Message);
      }
      catch (RegexMatchTimeoutException e) {
         Console.WriteLine("The operation timed out after {0:N0} milliseconds", 
                           e.MatchTimeout.TotalMilliseconds);
      }
   }
}

public class RegexUtilities
{
   public Tuple<int, double> GetWordData(string filename)
   { 
      const int MAX_TIMEOUT = 1000;   // Maximum timeout interval in milliseconds.
      const int INCREMENT = 350;      // Milliseconds increment of timeout.

      List<string> exclusions = new List<string>( new string[] { "a", "an", "the" });
      int[] wordLengths = new int[29];        // Allocate an array of more than ample size.
      string input = null;
      StreamReader sr = null;
      try { 
         sr = new StreamReader(filename);
         input = sr.ReadToEnd();
      }
      catch (FileNotFoundException e) {
         string msg = String.Format("Unable to find the file '{0}'", filename);
         throw new IOException(msg, e);
      }
      catch (IOException e) {
         throw new IOException(e.Message, e);
      }
      finally {
         if (sr != null) sr.Close(); 
      }

      int timeoutInterval = INCREMENT;
      bool init = false;
      Regex rgx = null;
      Match m = null;
      int indexPos = 0;  
      do {
         try {
            if (! init) {
               rgx = new Regex(@"\b\w+\b", RegexOptions.None, 
                               TimeSpan.FromMilliseconds(timeoutInterval));
               m = rgx.Match(input, indexPos);
               init = true;
            }
            else { 
               m = m.NextMatch();
            }
            if (m.Success) {    
               if ( !exclusions.Contains(m.Value.ToLower()))
                  wordLengths[m.Value.Length]++;

               indexPos += m.Length + 1;   
            }
         }
         catch (RegexMatchTimeoutException e) {
            if (e.MatchTimeout.TotalMilliseconds < MAX_TIMEOUT) {
               timeoutInterval += INCREMENT;
               init = false;
            }
            else {
               // Rethrow the exception.
               throw; 
            }   
         }          
      } while (m.Success);

      // If regex completed successfully, calculate number of words and average length.
      int nWords = 0; 
      long totalLength = 0;

      for (int ctr = wordLengths.GetLowerBound(0); ctr <= wordLengths.GetUpperBound(0); ctr++) {
         nWords += wordLengths[ctr];
         totalLength += ctr * wordLengths[ctr];
      }
      return new Tuple<int, double>(nWords, totalLength/nWords);
   }
}
```

```vb
Imports System.Collections.Generic
Imports System.IO
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim util As New RegexUtilities()
      Dim title As String = "Doyle - The Hound of the Baskervilles.txt"
      Try
         Dim info = util.GetWordData(title)
         Console.WriteLine("Words:               {0:N0}", info.Item1)
         Console.WriteLine("Average Word Length: {0:N2} characters", info.Item2) 
      Catch e As IOException
         Console.WriteLine("IOException reading file '{0}'", title)
         Console.WriteLine(e.Message)
      Catch e As RegexMatchTimeoutException
         Console.WriteLine("The operation timed out after {0:N0} milliseconds", 
                           e.MatchTimeout.TotalMilliseconds)
      End Try
   End Sub
End Module

Public Class RegexUtilities
   Public Function GetWordData(filename As String) As Tuple(Of Integer, Double) 
      Const MAX_TIMEOUT As Integer = 1000  ' Maximum timeout interval in milliseconds.
      Const INCREMENT As Integer = 350     ' Milliseconds increment of timeout.

      Dim exclusions As New List(Of String)({"a", "an", "the" })
      Dim wordLengths(30) As Integer        ' Allocate an array of more than ample size.
      Dim input As String = Nothing
      Dim sr As StreamReader = Nothing
      Try 
         sr = New StreamReader(filename)
         input = sr.ReadToEnd()
      Catch e As FileNotFoundException
         Dim msg As String = String.Format("Unable to find the file '{0}'", filename)
         Throw New IOException(msg, e)
      Catch e As IOException
         Throw New IOException(e.Message, e)
      Finally
         If sr IsNot Nothing Then sr.Close() 
      End Try

      Dim timeoutInterval As Integer = INCREMENT
      Dim init As Boolean = False
      Dim rgx As Regex = Nothing
      Dim m As Match = Nothing
      Dim indexPos As Integer = 0  
      Do
         Try
            If Not init Then
               rgx = New Regex("\b\w+\b", RegexOptions.None, 
                               TimeSpan.FromMilliseconds(timeoutInterval))
               m = rgx.Match(input, indexPos)
               init = True
            Else 
               m = m.NextMatch()
            End If
            If m.Success Then    
               If Not exclusions.Contains(m.Value.ToLower()) Then
                  wordLengths(m.Value.Length) += 1
               End If
               indexPos += m.Length + 1   
            End If
         Catch e As RegexMatchTimeoutException
            If e.MatchTimeout.TotalMilliseconds < MAX_TIMEOUT Then
               timeoutInterval += INCREMENT
               init = False
            Else
               ' Rethrow the exception.
               Throw 
            End If   
         End Try          
      Loop While m.Success

      ' If regex completed successfully, calculate number of words and average length.
      Dim nWords As Integer
      Dim totalLength As Long

      For ctr As Integer = wordLengths.GetLowerBound(0) To wordLengths.GetUpperBound(0)
         nWords += wordLengths(ctr)
         totalLength += ctr * wordLengths(ctr)
      Next
      Return New Tuple(Of Integer, Double)(nWords, totalLength/nWords)
   End Function
End Class
```

## <a name="capture-only-when-necessary"></a><span data-ttu-id="93303-297">Eseguire l'acquisizione solo quando necessario</span><span class="sxs-lookup"><span data-stu-id="93303-297">Capture only when necessary</span></span>

<span data-ttu-id="93303-298">Le espressioni regolari in .NET supportano diversi costrutti di raggruppamento, che consentono di raggruppare un modello di espressione regolare in una o più sottoespressioni.</span><span class="sxs-lookup"><span data-stu-id="93303-298">Regular expressions in .NET support a number of grouping constructs, which let you group a regular expression pattern into one or more subexpressions.</span></span> <span data-ttu-id="93303-299">I costrutti di raggruppamento più comunemente usati nel linguaggio delle espressioni regolari di .NET sono **(**_subexpression_**)** che definisce un gruppo di acquisizione numerato, e **(?<*_name_**>**_subexpression_**)**che definisce un gruppo di acquisizione denominato.</span><span class="sxs-lookup"><span data-stu-id="93303-299">The most commonly used grouping constructs in .NET regular expression language are **(**_subexpression_**)**, which defines a numbered capturing group, and **(?<*_name_**>**_subexpression_**)**, which defines a named capturing group.</span></span> <span data-ttu-id="93303-300">I costrutti di raggruppamento sono indispensabili per la creazione di backreference e per la definizione di una sottoespressione a cui viene applicato un quantificatore.</span><span class="sxs-lookup"><span data-stu-id="93303-300">Grouping constructs are essential for creating backreferences and for defining a subexpression to which a quantifier is applied.</span></span> 

<span data-ttu-id="93303-301">Tuttavia, l'utilizzo di questi elementi del linguaggio ha un costo.</span><span class="sxs-lookup"><span data-stu-id="93303-301">However, the use of these language elements has a cost.</span></span> <span data-ttu-id="93303-302">Comportano il popolamento dell'oggetto [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) restituito dalla proprietà [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) con le acquisizioni non denominate o denominate più recenti e se un singolo costrutto di raggruppamento ha acquisito più sottostringhe nella stringa di input comportano anche il popolamento dell'oggetto [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) restituito dalla proprietà [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) di un gruppo di acquisizione specifico con più oggetti [Capture](xref:System.Text.RegularExpressions.Capture).</span><span class="sxs-lookup"><span data-stu-id="93303-302">They cause the [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) object returned by the [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) property to be populated with the most recent unnamed or named captures, and if a single grouping construct has captured multiple substrings in the input string, they also populate the [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) object returned by the [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) property of a particular capturing group with multiple [Capture](xref:System.Text.RegularExpressions.Capture) objects.</span></span>

<span data-ttu-id="93303-303">I costrutti di raggruppamento spesso vengono utilizzati solo in un'espressione regolare in modo tale che sia possibile applicarvi i quantificatori e che i gruppi acquisiti da queste sottoespressioni non vengano utilizzati successivamente.</span><span class="sxs-lookup"><span data-stu-id="93303-303">Often, grouping constructs are used in a regular expression only so that quantifiers can be applied to them, and the groups captured by these subexpressions are not subsequently used.</span></span> <span data-ttu-id="93303-304">Ad esempio, l'espressione regolare `\b(\w+[;,]?\s?)+[.?!]` è progettata per acquisire un'intera frase.</span><span class="sxs-lookup"><span data-stu-id="93303-304">For example, the regular expression `\b(\w+[;,]?\s?)+[.?!]` is designed to capture an entire sentence.</span></span> <span data-ttu-id="93303-305">Nella tabella seguente sono descritti gli elementi del linguaggio del modello di espressione regolare e il relativo effetto sulle raccolte [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) e [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) dell'oggetto [Match](xref:System.Text.RegularExpressions.Match).</span><span class="sxs-lookup"><span data-stu-id="93303-305">The following table describes the language elements in this regular expression pattern and their effect on the [Match](xref:System.Text.RegularExpressions.Match) object's [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) and [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) collections.</span></span>

<span data-ttu-id="93303-306">Criterio</span><span class="sxs-lookup"><span data-stu-id="93303-306">Pattern</span></span> | <span data-ttu-id="93303-307">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93303-307">Description</span></span>
------- | -----------
`\b` | <span data-ttu-id="93303-308">Inizia la corrispondenza sul confine di parola.</span><span class="sxs-lookup"><span data-stu-id="93303-308">Begin the match at a word boundary.</span></span>
`\w+` | <span data-ttu-id="93303-309">Trova la corrispondenza di uno o più caratteri alfanumerici.</span><span class="sxs-lookup"><span data-stu-id="93303-309">Match one or more word characters.</span></span>
`[;,]?` | <span data-ttu-id="93303-310">Trova la corrispondenza di una o nessuna virgola oppure di uno o nessun punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="93303-310">Match zero or one comma or semicolon.</span></span>
`\s?` | <span data-ttu-id="93303-311">Trova la corrispondenza di uno o nessuno spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="93303-311">Match zero or one white-space character.</span></span>
`(\w+[;,]?\s?)+` | <span data-ttu-id="93303-312">Trova la corrispondenza di una o più occorrenze di uno o più caratteri alfanumerici seguiti da una virgola o un punto e virgola facoltativo seguito da uno spazio vuoto facoltativo.</span><span class="sxs-lookup"><span data-stu-id="93303-312">Match one or more occurrences of one or more word characters followed by an optional comma or semicolon followed by an optional white-space character.</span></span> <span data-ttu-id="93303-313">Questo modello definisce il primo gruppo di acquisizione, necessario affinché la combinazione di più caratteri alfanumerici, ovvero una parola, seguiti da un simbolo di punteggiatura facoltativo venga ripetuta finché il motore delle espressioni regolari non raggiunge la fine di una frase.</span><span class="sxs-lookup"><span data-stu-id="93303-313">This defines the first capturing group, which is necessary so that the combination of multiple word characters (that is, a word) followed by an optional punctuation symbol will be repeated until the regular expression engine reaches the end of a sentence.</span></span>
`[.?!]` | <span data-ttu-id="93303-314">Trova la corrispondenza di un punto, un punto interrogativo o un punto esclamativo.</span><span class="sxs-lookup"><span data-stu-id="93303-314">Match a period, question mark, or exclamation point.</span></span>
 
<span data-ttu-id="93303-315">Come illustrato nell'esempio seguente, quando viene trovata una corrispondenza, entrambi gli oggetti [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) e [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) vengono popolati con le acquisizioni della corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="93303-315">As the following example shows, when a match is found, both the [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) and [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) objects are populated with captures from the match.</span></span> <span data-ttu-id="93303-316">In questo caso, è presente il gruppo di acquisizione `(\w+[;,]?\s?)` in modo tale che sia possibile applicarvi il quantificatore **+** consentendo al criterio di espressione regolare di trovare la corrispondenza con ogni parola di una frase.</span><span class="sxs-lookup"><span data-stu-id="93303-316">In this case, the capturing group `(\w+[;,]?\s?)` exists so that the **+** quantifier can be applied to it, which enables the regular expression pattern to match each word in a sentence.</span></span> <span data-ttu-id="93303-317">In caso contrario, verrebbe trovata la corrispondenza con l'ultima parola di una frase.</span><span class="sxs-lookup"><span data-stu-id="93303-317">Otherwise, it would match the last word in a sentence.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is one sentence. This is another.";
      string pattern = @"\b(\w+[;,]?\s?)+[.?!]";

      foreach (Match match in Regex.Matches(input, pattern)) {
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index);
         int grpCtr = 0;
         foreach (Group grp in match.Groups) {
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index);
            int capCtr = 0;
            foreach (Capture cap in grp.Captures) {
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index);
               capCtr++;
            }
            grpCtr++;
         }          
         Console.WriteLine();        
      }
   }
}
// The example displays the following output:
//       Match: 'This is one sentence.' at index 0.
//          Group 0: 'This is one sentence.' at index 0.
//             Capture 0: 'This is one sentence.' at 0.
//          Group 1: 'sentence' at index 12.
//             Capture 0: 'This ' at 0.
//             Capture 1: 'is ' at 5.
//             Capture 2: 'one ' at 8.
//             Capture 3: 'sentence' at 12.
//       
//       Match: 'This is another.' at index 22.
//          Group 0: 'This is another.' at index 22.
//             Capture 0: 'This is another.' at 22.
//          Group 1: 'another' at index 30.
//             Capture 0: 'This ' at 22.
//             Capture 1: 'is ' at 27.
//             Capture 2: 'another' at 30.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is one sentence. This is another."
      Dim pattern As String = "\b(\w+[;,]?\s?)+[.?!]"

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index)
         Dim grpCtr As Integer = 0
         For Each grp As Group In match.Groups
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index)
            Dim capCtr As Integer = 0
            For Each cap As Capture In grp.Captures
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index)
               capCtr += 1
            Next
            grpCtr += 1
         Next          
         Console.WriteLine()        
      Next    
   End Sub
End Module
' The example displays the following output:
'       Match: 'This is one sentence.' at index 0.
'          Group 0: 'This is one sentence.' at index 0.
'             Capture 0: 'This is one sentence.' at 0.
'          Group 1: 'sentence' at index 12.
'             Capture 0: 'This ' at 0.
'             Capture 1: 'is ' at 5.
'             Capture 2: 'one ' at 8.
'             Capture 3: 'sentence' at 12.
'       
'       Match: 'This is another.' at index 22.
'          Group 0: 'This is another.' at index 22.
'             Capture 0: 'This is another.' at 22.
'          Group 1: 'another' at index 30.
'             Capture 0: 'This ' at 22.
'             Capture 1: 'is ' at 27.
'             Capture 2: 'another' at 30.
```

<span data-ttu-id="93303-318">Quando le sottoespressioni vengono utilizzate solo per applicarvi i quantificatori e non è necessario il testo acquisito, è consigliabile disabilitare le acquisizioni del gruppo.</span><span class="sxs-lookup"><span data-stu-id="93303-318">When you use subexpressions only to apply quantifiers to them, and you are not interested in the captured text, you should disable group captures.</span></span> <span data-ttu-id="93303-319">Ad esempio, l'elemento del linguaggio **(?:**_subexpression_**)** impedisce al gruppo al quale viene applicato di acquisire le sottostringhe corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="93303-319">For example, the **(?:**_subexpression_**)** language element prevents the group to which it applies from capturing matched substrings.</span></span> <span data-ttu-id="93303-320">Nell'esempio seguente il criterio di espressione regolare dell'esempio precedente viene modificato in `\b(?:\w+[;,]?\s?)+[.?!]`.</span><span class="sxs-lookup"><span data-stu-id="93303-320">In the following example, the regular expression pattern from the previous example is changed to `\b(?:\w+[;,]?\s?)+[.?!]`.</span></span> <span data-ttu-id="93303-321">Come illustrato nell'output, il motore delle espressioni regolari non popolerà le raccolte [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) e [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection).</span><span class="sxs-lookup"><span data-stu-id="93303-321">As the output shows, it prevents the regular expression engine from populating the [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) and [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) collections.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is one sentence. This is another.";
      string pattern = @"\b(?:\w+[;,]?\s?)+[.?!]";

      foreach (Match match in Regex.Matches(input, pattern)) {
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index);
         int grpCtr = 0;
         foreach (Group grp in match.Groups) {
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index);
            int capCtr = 0;
            foreach (Capture cap in grp.Captures) {
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index);
               capCtr++;
            }
            grpCtr++;
         }          
         Console.WriteLine();        
      }
   }
}
// The example displays the following output:
//       Match: 'This is one sentence.' at index 0.
//          Group 0: 'This is one sentence.' at index 0.
//             Capture 0: 'This is one sentence.' at 0.
//       
//       Match: 'This is another.' at index 22.
//          Group 0: 'This is another.' at index 22.
//             Capture 0: 'This is another.' at 22.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is one sentence. This is another."
      Dim pattern As String = "\b(?:\w+[;,]?\s?)+[.?!]"

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index)
         Dim grpCtr As Integer = 0
         For Each grp As Group In match.Groups
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index)
            Dim capCtr As Integer = 0
            For Each cap As Capture In grp.Captures
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index)
               capCtr += 1
            Next
            grpCtr += 1
         Next          
         Console.WriteLine()        
      Next    
   End Sub
End Module
' The example displays the following output:
'       Match: 'This is one sentence.' at index 0.
'          Group 0: 'This is one sentence.' at index 0.
'             Capture 0: 'This is one sentence.' at 0.
'       
'       Match: 'This is another.' at index 22.
'          Group 0: 'This is another.' at index 22.
'             Capture 0: 'This is another.' at 22.
```

<span data-ttu-id="93303-322">È possibile disabilitare le acquisizioni in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="93303-322">You can disable captures in one of the following ways:</span></span>

* <span data-ttu-id="93303-323">Usare l'elemento del linguaggio **(?:**_subexpression_**)**.</span><span class="sxs-lookup"><span data-stu-id="93303-323">Use the **(?:**_subexpression_**)** language element.</span></span> <span data-ttu-id="93303-324">Questo elemento impedisce l'acquisizione delle sottostringhe corrispondenti nel gruppo a cui viene applicato.</span><span class="sxs-lookup"><span data-stu-id="93303-324">This element prevents the capture of matched substrings in the group to which it applies.</span></span> <span data-ttu-id="93303-325">Non disabilita le acquisizioni delle sottostringhe in tutti i gruppi annidati.</span><span class="sxs-lookup"><span data-stu-id="93303-325">It does not disable substring captures in any nested groups.</span></span>

* <span data-ttu-id="93303-326">Usare l'opzione [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture).</span><span class="sxs-lookup"><span data-stu-id="93303-326">Use the [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) option.</span></span> <span data-ttu-id="93303-327">Disabilita tutte le acquisizioni non denominate o implicite nel modello di espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="93303-327">It disables all unnamed or implicit captures in the regular expression pattern.</span></span> <span data-ttu-id="93303-328">Quando si usa questa opzione, è possibile acquisire solo le sottostringhe che corrispondono ai gruppi denominati definiti con l'elemento del linguaggio **(?<**_name_**>**_subexpression_**)**.</span><span class="sxs-lookup"><span data-stu-id="93303-328">When you use this option, only substrings that match named groups defined with the **(?<**_name_**>**_subexpression_**)** language element can be captured.</span></span> <span data-ttu-id="93303-329">Il flag [ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) può essere passato al parametro options di un costruttore di classe [Regex](xref:System.Text.RegularExpressions.Regex) o al parametro options di un metodo di corrispondenza statico [Regex](xref:System.Text.RegularExpressions.Regex).</span><span class="sxs-lookup"><span data-stu-id="93303-329">The [ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) flag can be passed to the options parameter of a [Regex](xref:System.Text.RegularExpressions.Regex) class constructor or to the options parameter of a [Regex](xref:System.Text.RegularExpressions.Regex) static matching method.</span></span>

* <span data-ttu-id="93303-330">Usare l'opzione **n** nell'elemento del linguaggio **(?imnsx)**.</span><span class="sxs-lookup"><span data-stu-id="93303-330">Use the **n** option in the **(?imnsx)** language element.</span></span> <span data-ttu-id="93303-331">Questa opzione disabilita tutte le acquisizioni non denominate o implicite dal punto nel modello di espressione regolare in corrispondenza del quale viene visualizzato l'elemento.</span><span class="sxs-lookup"><span data-stu-id="93303-331">This option disables all unnamed or implicit captures from the point in the regular expression pattern at which the element appears.</span></span> <span data-ttu-id="93303-332">Le acquisizioni vengono disabilitate fino alla fine del modello o finché l'opzione **(-n)** non abilita le acquisizioni non denominate o implicite.</span><span class="sxs-lookup"><span data-stu-id="93303-332">Captures are disabled either until the end of the pattern or until the **(-n)** option enables unnamed or implicit captures.</span></span> <span data-ttu-id="93303-333">Per altre informazioni, vedere [Costrutti vari nelle espressioni regolari](miscellaneous.md).</span><span class="sxs-lookup"><span data-stu-id="93303-333">For more information, see [Miscellaneous constructs in regular expressions](miscellaneous.md).</span></span>

* <span data-ttu-id="93303-334">Usare l'opzione **n** nell'elemento del linguaggio **(?imnsx:**_subexpression_**)**.</span><span class="sxs-lookup"><span data-stu-id="93303-334">Use the **n** option in the **(?imnsx:**_subexpression_**)** language element.</span></span> <span data-ttu-id="93303-335">Questa opzione disabilita tutte le acquisizioni non denominate o implicite in *subexpression*.</span><span class="sxs-lookup"><span data-stu-id="93303-335">This option disables all unnamed or implicit captures in *subexpression*.</span></span> <span data-ttu-id="93303-336">Vengono inoltre disabilitate tutte le acquisizioni dai gruppi di acquisizione annidati non denominati o impliciti.</span><span class="sxs-lookup"><span data-stu-id="93303-336">Captures by any unnamed or implicit nested capturing groups are disabled as well.</span></span>

## <a name="related-topics"></a><span data-ttu-id="93303-337">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="93303-337">Related topics</span></span>

<span data-ttu-id="93303-338">Titolo</span><span class="sxs-lookup"><span data-stu-id="93303-338">Title</span></span> | <span data-ttu-id="93303-339">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93303-339">Description</span></span>
----- | ----------- 
[<span data-ttu-id="93303-340">Dettagli sul comportamento delle espressioni regolari</span><span class="sxs-lookup"><span data-stu-id="93303-340">Details of regular expression behavior</span></span>](regex-behavior.md) | <span data-ttu-id="93303-341">Viene esaminata l'implementazione del motore delle espressioni regolari in .NET.</span><span class="sxs-lookup"><span data-stu-id="93303-341">Examines the implementation of the regular expression engine in .NET.</span></span> <span data-ttu-id="93303-342">L'argomento è incentrato sulla flessibilità delle espressioni regolari e sulla responsabilità dello sviluppatore al fine di garantire un funzionamento efficace e affidabile del motore delle espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="93303-342">The topic focuses on the flexibility of regular expressions and explains the developer's responsibility for ensuring the efficient and robust operation of the regular expression engine.</span></span>
[<span data-ttu-id="93303-343">Backtracking nelle espressioni regolari</span><span class="sxs-lookup"><span data-stu-id="93303-343">Backtracking in regular expressions</span></span>](backtracking.md) | <span data-ttu-id="93303-344">Viene illustrato il backtracking e il modo in cui influisce sulle prestazioni delle espressioni regolari e vengono esaminati gli elementi del linguaggio che forniscono le alternative al backtracking.</span><span class="sxs-lookup"><span data-stu-id="93303-344">Explains what backtracking is and how it affects regular expression performance, and examines language elements that provide alternatives to backtracking.</span></span>
[<span data-ttu-id="93303-345">Linguaggio di espressioni regolari - Riferimento rapido</span><span class="sxs-lookup"><span data-stu-id="93303-345">Regular expression language - quick reference</span></span>](quick-ref.md) | <span data-ttu-id="93303-346">Vengono illustrati gli elementi del linguaggio delle espressioni regolari in .NET e vengono forniti i collegamenti alla documentazione dettagliata per ogni elemento del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="93303-346">Describes the elements of the regular expression language in .NET and provides links to detailed documentation for each language element.</span></span>
 


