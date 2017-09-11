---
title: Formattazione di tipi
description: Formattazione di tipi
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: cf497639-9f91-45cb-836f-998d1cea2f43
ms.translationtype: Human Translation
ms.sourcegitcommit: b967d8e55347f44a012e4ad8e916440ae228c8ec
ms.openlocfilehash: e9b8ad13a48dd43236769b130d6f8a75b7b023ca
ms.contentlocale: it-it
ms.lasthandoff: 03/10/2017

---

# <a name="formatting-types"></a><span data-ttu-id="7574e-104">Formattazione di tipi</span><span class="sxs-lookup"><span data-stu-id="7574e-104">Formatting types</span></span>

<span data-ttu-id="7574e-105">La formattazione è il processo di conversione di un'istanza di una classe, una struttura o un valore di enumerazione nella relativa rappresentazione di stringa, eseguito spesso in modo che la stringa risultante possa essere visualizzata dagli utenti o deserializzata per ripristinare il tipo di dati originale.</span><span class="sxs-lookup"><span data-stu-id="7574e-105">Formatting is the process of converting an instance of a class, structure, or enumeration value to its string representation, often so that the resulting string can be displayed to users or deserialized to restore the original data type.</span></span> <span data-ttu-id="7574e-106">Questa conversione può comportare le difficoltà seguenti:</span><span class="sxs-lookup"><span data-stu-id="7574e-106">This conversion can pose a number of challenges:</span></span>

* <span data-ttu-id="7574e-107">Il modo in cui i valori vengono archiviati internamente non riflette necessariamente il modo in cui gli utenti desiderano visualizzarli.</span><span class="sxs-lookup"><span data-stu-id="7574e-107">The way that values are stored internally does not necessarily reflect the way that users want to view them.</span></span> <span data-ttu-id="7574e-108">Un numero di telefono potrebbe ad esempio venire archiviato nel formato **8009999999**, che non è di immediata comprensione.</span><span class="sxs-lookup"><span data-stu-id="7574e-108">For example, a telephone number might be stored in the form **8009999999**, which is not user-friendly.</span></span> <span data-ttu-id="7574e-109">Potrebbe invece essere preferibile visualizzarlo come **800-999-9999**.</span><span class="sxs-lookup"><span data-stu-id="7574e-109">It should instead be displayed as **800-999-9999**.</span></span> <span data-ttu-id="7574e-110">Per un esempio relativo all'applicazione di questo formato a un numero, vedere la sezione [Stringhe di formato personalizzate](#custom-format-strings).</span><span class="sxs-lookup"><span data-stu-id="7574e-110">See the [Custom format strings](#custom-format-strings) section for an example that formats a number in this way.</span></span> 

* <span data-ttu-id="7574e-111">La conversione di un oggetto nella relativa rappresentazione di stringa non è sempre intuitiva.</span><span class="sxs-lookup"><span data-stu-id="7574e-111">Sometimes the conversion of an object to its string representation is not intuitive.</span></span> <span data-ttu-id="7574e-112">Non è ad esempio chiaro come dovrebbe venire visualizzata la rappresentazione di stringa di un oggetto **Temperature** o di un oggetto **Person**.</span><span class="sxs-lookup"><span data-stu-id="7574e-112">For example, it is not clear how the string representation of a **Temperature** object or a **Person** object should appear.</span></span> <span data-ttu-id="7574e-113">Per un esempio in cui un oggetto **Temperature** viene formattato in modi diversi, vedere la sezione [Stringhe di formato standard](#standard-format-strings).</span><span class="sxs-lookup"><span data-stu-id="7574e-113">For an example that formats a **Temperature** object in a variety of ways, see the [Standard format strings](#standard-format-strings) section.</span></span>

* <span data-ttu-id="7574e-114">I valori richiedono spesso una formattazione dipendente dalle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="7574e-114">Values often require culture-sensitive formatting.</span></span> <span data-ttu-id="7574e-115">In un'applicazione in cui vengono usati i numeri per riflettere valori monetari, ad esempio, le stringhe numeriche devono includere il simbolo di valuta, il separatore di gruppi, che nella maggior parte delle impostazioni cultura corrisponde al separatore delle migliaia, e il separatore decimale delle impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="7574e-115">For example, in an application that uses numbers to reflect monetary values, numeric strings should include the current culture’s currency symbol, group separator (which, in most cultures, is the thousands separator), and decimal symbol.</span></span> <span data-ttu-id="7574e-116">Per un esempio, vedere la sezione [Formattazione dipendente dalle impostazioni cultura con provider di formato e l'interfaccia IFormatProvider](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface).</span><span class="sxs-lookup"><span data-stu-id="7574e-116">For an example, see the [Culture-sensitive formatting with format providers and the IFormatProvider interface](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface) section.</span></span> 

* <span data-ttu-id="7574e-117">È possibile che in un'applicazione lo stesso valore debba essere visualizzato in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="7574e-117">An application may have to display the same value in different ways.</span></span> <span data-ttu-id="7574e-118">È ad esempio possibile che un membro di enumerazione venga rappresentato visualizzando una rappresentazione di stringa del relativo nome oppure visualizzando il relativo valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="7574e-118">For example, an application may represent an enumeration member by displaying a string representation of its name or by displaying its underlying value.</span></span> <span data-ttu-id="7574e-119">Per un esempio in cui un membro dell'enumerazione [DayOfWeek](xref:System.DayOfWeek) viene formattato in modi diversi, vedere la sezione [Stringhe di formato standard](#standard-format-strings).</span><span class="sxs-lookup"><span data-stu-id="7574e-119">For an example that formats a member of the [DayOfWeek](xref:System.DayOfWeek) enumeration in different ways, see the [Standard format strings](#standard-format-strings) section.</span></span>

<span data-ttu-id="7574e-120">In .NET è disponibile un supporto avanzato della formattazione che consente agli sviluppatori di soddisfare questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="7574e-120">.NET provides rich formatting support that enables developers to address these requirements.</span></span> 

> [!NOTE]
> <span data-ttu-id="7574e-121">La formattazione consente di convertire il valore di un tipo in una rappresentazione di stringa,</span><span class="sxs-lookup"><span data-stu-id="7574e-121">Formatting converts the value of a type into a string representation.</span></span> <span data-ttu-id="7574e-122">mentre l'analisi è l'operazione inversa.</span><span class="sxs-lookup"><span data-stu-id="7574e-122">Parsing is the inverse of formatting.</span></span> <span data-ttu-id="7574e-123">Un'operazione di analisi consente di creare un'istanza di un tipo di dati dalla relativa rappresentazione di stringa.</span><span class="sxs-lookup"><span data-stu-id="7574e-123">A parsing operation creates an instance of a data type from its string representation.</span></span> <span data-ttu-id="7574e-124">Per informazioni sulla conversione di stringhe in altri tipi di dati, vedere [Analisi di stringhe](parsing-strings.md).</span><span class="sxs-lookup"><span data-stu-id="7574e-124">For information about converting strings to other data types, see [Parsing strings](parsing-strings.md).</span></span>

<span data-ttu-id="7574e-125">In questa panoramica sono incluse le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7574e-125">This overview contains the following sections:</span></span>

* [<span data-ttu-id="7574e-126">Formattazione in .NET</span><span class="sxs-lookup"><span data-stu-id="7574e-126">Formatting in .NET</span></span>](#formatting-in-net)

* [<span data-ttu-id="7574e-127">Formattazione predefinita tramite il metodo ToString</span><span class="sxs-lookup"><span data-stu-id="7574e-127">Default formatting using the ToString method</span></span>](#default-formatting-using-the-tostring-method)

* [<span data-ttu-id="7574e-128">Override del metodo ToString</span><span class="sxs-lookup"><span data-stu-id="7574e-128">Overriding the ToString method</span></span>](#overriding-the-tostring-method)

* [<span data-ttu-id="7574e-129">Metodo ToString e stringhe di formato</span><span class="sxs-lookup"><span data-stu-id="7574e-129">The ToString method and format strings</span></span>](#the-tostring-method-and-format-strings)

    * [<span data-ttu-id="7574e-130">Stringhe di formato standard</span><span class="sxs-lookup"><span data-stu-id="7574e-130">Standard format strings</span></span>](#standard-format-strings)
    
    * [<span data-ttu-id="7574e-131">Stringhe di formato personalizzate</span><span class="sxs-lookup"><span data-stu-id="7574e-131">Custom format strings</span></span>](#custom-format-strings)
    
    * [<span data-ttu-id="7574e-132">Stringhe di formato e tipi .NET</span><span class="sxs-lookup"><span data-stu-id="7574e-132">Format strings and .NET types</span></span>](#format-strings-and-net-types)
    
* [<span data-ttu-id="7574e-133">Formattazione dipendente dalle impostazioni cultura con provider di formato e l'interfaccia IFormatProvider</span><span class="sxs-lookup"><span data-stu-id="7574e-133">Culture-sensitive formatting with format providers and the IFormatProvider interface</span></span>](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface)

    * [<span data-ttu-id="7574e-134">Formattazione dipendente dalle impostazioni cultura di valori numerici</span><span class="sxs-lookup"><span data-stu-id="7574e-134">Culture-sensitive formatting of numeric values</span></span>](#culture-sensitive-formatting-of-numeric-values)
    
    * [<span data-ttu-id="7574e-135">Formattazione dipendente dalle impostazioni cultura di valori data e ora</span><span class="sxs-lookup"><span data-stu-id="7574e-135">Culture-sensitive formatting of date and time values</span></span>](#culture-sensitive-formatting-of-date-and-time-values)
    
* [<span data-ttu-id="7574e-136">Interfaccia IFormattable</span><span class="sxs-lookup"><span data-stu-id="7574e-136">The IFormattable interface</span></span>](#the-iformattable-interface)

* [<span data-ttu-id="7574e-137">Formattazione composita</span><span class="sxs-lookup"><span data-stu-id="7574e-137">Composite formatting</span></span>](#composite-formatting)

* [<span data-ttu-id="7574e-138">Formattazione personalizzata con ICustomFormatter</span><span class="sxs-lookup"><span data-stu-id="7574e-138">Custom formatting with ICustomFormatter</span></span>](#custom-formatting-with-icustomformatter)

* [<span data-ttu-id="7574e-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7574e-139">Related topics</span></span>](#related-topics)

* [<span data-ttu-id="7574e-140">Riferimento</span><span class="sxs-lookup"><span data-stu-id="7574e-140">Reference</span></span>](#reference)

## <a name="formatting-in-net"></a><span data-ttu-id="7574e-141">Formattazione in .NET</span><span class="sxs-lookup"><span data-stu-id="7574e-141">Formatting in .NET</span></span>

<span data-ttu-id="7574e-142">Il meccanismo di base per la formattazione è costituito dall'implementazione predefinita del metodo [Object.ToString](xref:System.Object.ToString), illustrato nella sezione [Formattazione predefinita tramite il metodo ToString](#default-formatting-using-the-tostring-method) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="7574e-142">The basic mechanism for formatting is the default implementation of the [Object.ToString](xref:System.Object.ToString) method, which is discussed in the [Default formatting using the ToString method](#default-formatting-using-the-tostring-method) section later in this topic.</span></span> <span data-ttu-id="7574e-143">In .NET sono tuttavia disponibili diversi metodi per modificare ed estendere il supporto predefinito della formattazione,</span><span class="sxs-lookup"><span data-stu-id="7574e-143">However, .NET provides several ways to modify and extend its default formatting support.</span></span> <span data-ttu-id="7574e-144">tra cui:</span><span class="sxs-lookup"><span data-stu-id="7574e-144">These include the following:</span></span>

* <span data-ttu-id="7574e-145">Override del metodo [Object.ToString](xref:System.Object.ToString) per definire una rappresentazione di stringa personalizzata del valore di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="7574e-145">Overriding the [Object.ToString](xref:System.Object.ToString) method to define a custom string representation of an object’s value.</span></span> <span data-ttu-id="7574e-146">Per altre informazioni, vedere la sezione [Override del metodo ToString](#overriding-the-tostring-method) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="7574e-146">For more information, see the [Overriding the ToString method](#overriding-the-tostring-method) section later in this topic.</span></span>

* <span data-ttu-id="7574e-147">Definizione di identificatori di formato che consentono l'assunzione di più forme da parte della rappresentazione di stringa del valore di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="7574e-147">Defining format specifiers that enable the string representation of an object’s value to take multiple forms.</span></span> <span data-ttu-id="7574e-148">L'identificatore di formato "X" nell'istruzione seguente consente, ad esempio, di convertire un valore intero nella rappresentazione di stringa di un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="7574e-148">For example, the "X" format specifier in the following statement converts an integer to the string representation of a hexadecimal value.</span></span>

  ```csharp
  int integerValue = 60312;
  Console.WriteLine(integerValue.ToString("X"));   // Displays EB98.
  ```

  ```vb
  Dim integerValue As Integer = 60312
  Console.WriteLine(integerValue.ToString("X"))   ' Displays EB98.
  ```
  
  <span data-ttu-id="7574e-149">Per altre informazioni sugli identificatori di formato, vedere la sezione [Metodo ToString e stringhe di formato](#the-tostring-method-and-format-strings).</span><span class="sxs-lookup"><span data-stu-id="7574e-149">For more information about format specifiers, see the [The ToString method and format strings](#the-tostring-method-and-format-strings) section.</span></span>
  
* <span data-ttu-id="7574e-150">Uso di provider di formato per sfruttare le convenzioni di formattazione di impostazioni cultura specifiche.</span><span class="sxs-lookup"><span data-stu-id="7574e-150">Using format providers to take advantage of the formatting conventions of a specific culture.</span></span> <span data-ttu-id="7574e-151">Nell'istruzione seguente, ad esempio, viene visualizzato un valore di valuta usando le convenzioni di formattazione delle impostazioni cultura en-US.</span><span class="sxs-lookup"><span data-stu-id="7574e-151">For example, the following statement displays a currency value by using the formatting conventions of the en-US culture.</span></span> 

  ```csharp
  double cost = 1632.54; 
  Console.WriteLine(cost.ToString("C", 
                  new System.Globalization.CultureInfo("en-US")));   
  // The example displays the following output:
  //       $1,632.54
  ```

  ```vb
  Dim cost As Double = 1632.54
  Console.WriteLine(cost.ToString("C", New System.Globalization.CultureInfo("en-US")))
  ' The example displays the following output:
  '       $1,632.54
  ```
  
  <span data-ttu-id="7574e-152">Per altre informazioni sulla formattazione con i provider di formato, vedere la sezione [Formattazione dipendente dalle impostazioni cultura con provider di formato e l'interfaccia IFormatProvider](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface).</span><span class="sxs-lookup"><span data-stu-id="7574e-152">For more information about formatting with format providers, see the [Culture-sensitive formatting with format providers and the IFormatProvider interface](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface) section.</span></span>  
  
* <span data-ttu-id="7574e-153">Implementazione dell'interfaccia [IFormattable](xref:System.IFormattable) per supportare sia la conversione di stringa con la classe [Convert](xref:System.Convert) che la formattazione composita.</span><span class="sxs-lookup"><span data-stu-id="7574e-153">Implementing the [IFormattable](xref:System.IFormattable) interface to support both string conversion with the [Convert](xref:System.Convert) class and composite formatting.</span></span> <span data-ttu-id="7574e-154">Per altre informazioni, vedere la sezione [Interfaccia IFormattable](#the-iformattable-interface).</span><span class="sxs-lookup"><span data-stu-id="7574e-154">For more information, see the [The IFormattable interface](#the-iformattable-interface) section.</span></span>

* <span data-ttu-id="7574e-155">Uso della formattazione composita per incorporare la rappresentazione di stringa di un valore in una stringa di dimensioni maggiori.</span><span class="sxs-lookup"><span data-stu-id="7574e-155">Using composite formatting to embed the string representation of a value in a larger string.</span></span> <span data-ttu-id="7574e-156">Per altre informazioni, vedere la sezione [Formattazione composita](#composite-formatting).</span><span class="sxs-lookup"><span data-stu-id="7574e-156">For more information, see the [Composite formatting](#composite-formatting) section.</span></span>

* <span data-ttu-id="7574e-157">Implementazione di [ICustomFormatter](xref:System.ICustomFormatter) e [IFormatProvider](xref:System.IFormatProvider) per offrire una soluzione di formattazione personalizzata completa.</span><span class="sxs-lookup"><span data-stu-id="7574e-157">Implementing [ICustomFormatter](xref:System.ICustomFormatter) and [IFormatProvider](xref:System.IFormatProvider) to provide a complete custom formatting solution.</span></span> <span data-ttu-id="7574e-158">Per altre informazioni, vedere la sezione [Formattazione personalizzata con ICustomFormatter](#custom-formatting-with-icustomformatter).</span><span class="sxs-lookup"><span data-stu-id="7574e-158">For more information, see the [Custom formatting with ICustomFormatter](#custom-formatting-with-icustomformatter) section.</span></span>

<span data-ttu-id="7574e-159">Nelle sezioni seguenti vengono esaminati questi metodi per la conversione di un oggetto nella relativa rappresentazione di stringa.</span><span class="sxs-lookup"><span data-stu-id="7574e-159">The following sections examine these methods for converting an object to its string representation.</span></span>

## <a name="default-formatting-using-the-tostring-method"></a><span data-ttu-id="7574e-160">Formattazione predefinita tramite il metodo ToString</span><span class="sxs-lookup"><span data-stu-id="7574e-160">Default formatting using the ToString method</span></span>

<span data-ttu-id="7574e-161">Ogni tipo derivato da [System.Object](xref:System.Object) eredita automaticamente un metodo [ToString](xref:System.Object.ToString) senza parametri che, per impostazione predefinita, restituisce il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="7574e-161">Every type that is derived from [System.Object](xref:System.Object) automatically inherits a parameterless [ToString](xref:System.Object.ToString) method, which returns the name of the type by default.</span></span> <span data-ttu-id="7574e-162">Nell'esempio seguente viene illustrato il metodo [ToString](xref:System.Object.ToString) predefinito.</span><span class="sxs-lookup"><span data-stu-id="7574e-162">The following example illustrates the default [ToString](xref:System.Object.ToString) method.</span></span> <span data-ttu-id="7574e-163">Viene definita una classe denominata `Automobile` che non dispone di implementazione.</span><span class="sxs-lookup"><span data-stu-id="7574e-163">It defines a class named `Automobile` that has no implementation.</span></span> <span data-ttu-id="7574e-164">Quando viene creata un'istanza della classe e viene chiamato il relativo metodo [ToString](xref:System.Object.ToString), viene visualizzato il nome del tipo relativo.</span><span class="sxs-lookup"><span data-stu-id="7574e-164">When the class is instantiated and its [ToString](xref:System.Object.ToString) method is called, it displays its type name.</span></span> <span data-ttu-id="7574e-165">Si noti che il metodo [ToString](xref:System.Object.ToString) non viene chiamato in modo esplicito nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="7574e-165">Note that the [ToString](xref:System.Object.ToString) method is not explicitly called in the example.</span></span> <span data-ttu-id="7574e-166">Il metodo [Console.WriteLine(Object)](xref:System.Console.WriteLine(System.Object)) chiama in modo implicito il metodo [ToString](xref:System.Object.ToString) dell'oggetto passato come argomento.</span><span class="sxs-lookup"><span data-stu-id="7574e-166">The [Console.WriteLine(Object)](xref:System.Console.WriteLine(System.Object)) method implicitly calls the [ToString](xref:System.Object.ToString) method of the object passed to it as an argument.</span></span> 

```csharp
using System;

public class Automobile
{
   // No implementation. All members are inherited from Object.
}

public class Example
{
   public static void Main()
   {
      Automobile firstAuto = new Automobile();
      Console.WriteLine(firstAuto);
   }
}
// The example displays the following output:
//       Automobile
```

```vb 
Public Class Automobile
   ' No implementation. All members are inherited from Object.
End Class

Module Example
   Public Sub Main()
      Dim firstAuto As New Automobile()
      Console.WriteLine(firstAuto)
   End Sub
End Module
' The example displays the following output:
'       Automobile
```

<span data-ttu-id="7574e-167">Poiché tutti i tipi diversi dalle interfacce sono derivati da [Object](xref:System.Object), questa funzionalità viene fornita automaticamente alle classi o alle strutture personalizzate.</span><span class="sxs-lookup"><span data-stu-id="7574e-167">Because all types other than interfaces are derived from [Object](xref:System.Object), this functionality is automatically provided to your custom classes or structures.</span></span> <span data-ttu-id="7574e-168">La funzionalità offerta dal metodo [ToString](xref:System.Object.ToString) predefinito è tuttavia limitata poiché non fornisce informazioni su un'istanza del tipo sebbene consenta di identificarlo.</span><span class="sxs-lookup"><span data-stu-id="7574e-168">However, the functionality offered by the default [ToString](xref:System.Object.ToString) method, is limited: Although it identifies the type, it fails to provide any information about an instance of the type.</span></span> <span data-ttu-id="7574e-169">Per fornire una rappresentazione di stringa di un oggetto che offra informazioni sull'oggetto, è necessario eseguire l'override del metodo [ToString](xref:System.Object.ToString).</span><span class="sxs-lookup"><span data-stu-id="7574e-169">To provide a string representation of an object that provides information about that object, you must override the [ToString](xref:System.Object.ToString) method.</span></span>

> [!NOTE]
> <span data-ttu-id="7574e-170">Le strutture ereditano dall'oggetto [ValueType](xref:System.ValueType), che a sua volta viene derivato da [Object](xref:System.Object).</span><span class="sxs-lookup"><span data-stu-id="7574e-170">Structures inherit from [ValueType](xref:System.ValueType), which in turn is derived from [Object](xref:System.Object).</span></span> <span data-ttu-id="7574e-171">Sebbene [ValueType](xref:System.ValueType) esegua l'override di [Object.ToString](xref:System.Object.ToString), l'implementazione è identica.</span><span class="sxs-lookup"><span data-stu-id="7574e-171">Although [ValueType](xref:System.ValueType) overrides [Object.ToString](xref:System.Object.ToString), its implementation is identical.</span></span>

## <a name="overriding-the-tostring-method"></a><span data-ttu-id="7574e-172">Override del metodo ToString</span><span class="sxs-lookup"><span data-stu-id="7574e-172">Overriding the ToString method</span></span>

<span data-ttu-id="7574e-173">La visualizzazione del nome di un tipo ha spesso un uso limitato e non consente agli utenti dei tipi di distinguere tra le istanze.</span><span class="sxs-lookup"><span data-stu-id="7574e-173">Displaying the name of a type is often of limited use and does not allow consumers of your types to differentiate one instance from another.</span></span> <span data-ttu-id="7574e-174">È tuttavia possibile eseguire l'override del metodo [ToString](xref:System.Object.ToString) per offrire una rappresentazione più utile del valore di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="7574e-174">However, you can override the [ToString](xref:System.Object.ToString) method to provide a more useful representation of an object’s value.</span></span> <span data-ttu-id="7574e-175">Nell'esempio seguente viene definito un oggetto `Temperature` e viene eseguito l'override del relativo metodo [ToString](xref:System.Object.ToString) per visualizzare la temperatura in gradi Celsius.</span><span class="sxs-lookup"><span data-stu-id="7574e-175">The following example defines a `Temperature` object and overrides its [ToString](xref:System.Object.ToString) method to display the temperature in degrees Celsius.</span></span>

```csharp
using System;

public class Temperature
{
   private decimal temp;

   public Temperature(decimal temperature)
   {
      this.temp = temperature;   
   }

   public override string ToString()
   {
      return this.temp.ToString("N1") + "°C";
   }
}

public class Example
{
   public static void Main()
   {
      Temperature currentTemperature = new Temperature(23.6m);
      Console.WriteLine("The current temperature is " +
                        currentTemperature.ToString());
   }
}
// The example displays the following output:
//       The current temperature is 23.6°C.
```

```vb
Public Class Temperature
   Private temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.temp = temperature
   End Sub

   Public Overrides Function ToString() As String
      Return Me.temp.ToString("N1") + "°C"   
   End Function
End Class

Module Example
   Public Sub Main()
      Dim currentTemperature As New Temperature(23.6d)
      Console.WriteLine("The current temperature is " +
                        currentTemperature.ToString())
   End Sub
End Module
' The example displays the following output:
'       The current temperature is 23.6°C.
```

<span data-ttu-id="7574e-176">In .NET è stato eseguito l'override del metodo [ToString](xref:System.Object.ToString) di ogni tipo di valore primitivo per visualizzare il valore dell'oggetto anziché il relativo nome.</span><span class="sxs-lookup"><span data-stu-id="7574e-176">In .NET, the [ToString](xref:System.Object.ToString) method of each primitive value type has been overridden to display the object’s value instead of its name.</span></span> <span data-ttu-id="7574e-177">Nella tabella seguente viene illustrato l'override per ogni tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="7574e-177">The following table shows the override for each primitive type.</span></span> <span data-ttu-id="7574e-178">Si noti che la maggior parte dei metodi sottoposti a override chiama un altro overload del metodo [ToString](xref:System.Object.ToString) e passa a esso l'identificatore di formato "G", che definisce il formato generale per il tipo, e un oggetto [IFormatProvider](xref:System.IFormatProvider), che rappresenta le impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="7574e-178">Note that most of the overridden methods call another overload of the [ToString](xref:System.Object.ToString) method and pass it the "G" format specifier, which defines the general format for its type, and an [IFormatProvider](xref:System.IFormatProvider) object that represents the current culture.</span></span>

<span data-ttu-id="7574e-179">Tipo</span><span class="sxs-lookup"><span data-stu-id="7574e-179">Type</span></span> | <span data-ttu-id="7574e-180">Override di ToString</span><span class="sxs-lookup"><span data-stu-id="7574e-180">ToString override</span></span>
---- | -----------------
[<span data-ttu-id="7574e-181">Boolean</span><span class="sxs-lookup"><span data-stu-id="7574e-181">Boolean</span></span>](xref:System.Boolean) | <span data-ttu-id="7574e-182">Restituisce [Boolean.TrueString](xref:System.Boolean.TrueString) o [Boolean.FalseString](xref:System.Boolean.FalseString).</span><span class="sxs-lookup"><span data-stu-id="7574e-182">Returns either [Boolean.TrueString](xref:System.Boolean.TrueString) or [Boolean.FalseString](xref:System.Boolean.FalseString).</span></span>
[<span data-ttu-id="7574e-183">Byte</span><span class="sxs-lookup"><span data-stu-id="7574e-183">Byte</span></span>](xref:System.Byte) | <span data-ttu-id="7574e-184">Chiama `Byte.ToString("G", NumberFormatInfo.CurrentInfo)` per formattare il valore [Byte](xref:System.Byte) per le impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="7574e-184">Calls `Byte.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Byte](xref:System.Byte) value for the current culture.</span></span>
[<span data-ttu-id="7574e-185">Char</span><span class="sxs-lookup"><span data-stu-id="7574e-185">Char</span></span>](xref:System.Char) | <span data-ttu-id="7574e-186">Restituisce il carattere come stringa.</span><span class="sxs-lookup"><span data-stu-id="7574e-186">Returns the character as a string.</span></span>
[<span data-ttu-id="7574e-187">DateTime</span><span class="sxs-lookup"><span data-stu-id="7574e-187">DateTime</span></span>](xref:System.DateTime) | <span data-ttu-id="7574e-188">Chiama `DateTime.ToString("G", DatetimeFormatInfo.CurrentInfo)` per formattare il valore di data e ora per le impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="7574e-188">Calls `DateTime.ToString("G", DatetimeFormatInfo.CurrentInfo)` to format the date and time value for the current culture.</span></span> 
[<span data-ttu-id="7574e-189">Decimal</span><span class="sxs-lookup"><span data-stu-id="7574e-189">Decimal</span></span>](xref:System.Decimal) | <span data-ttu-id="7574e-190">Chiama `Decimal.ToString("G", NumberFormatInfo.CurrentInfo)` per formattare il valore [Decimal](xref:System.Decimal) per le impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="7574e-190">Calls `Decimal.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Decimal](xref:System.Decimal) value for the current culture.</span></span>
[<span data-ttu-id="7574e-191">Double</span><span class="sxs-lookup"><span data-stu-id="7574e-191">Double</span></span>](xref:System.Double) | <span data-ttu-id="7574e-192">Chiama `Double.ToString("G", NumberFormatInfo.CurrentInfo)` per formattare il valore [Double](xref:System.Double) per le impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="7574e-192">Calls `Double.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Double](xref:System.Double) value for the current culture.</span></span>
[<span data-ttu-id="7574e-193">Int16</span><span class="sxs-lookup"><span data-stu-id="7574e-193">Int16</span></span>](xref:System.Int16) | <span data-ttu-id="7574e-194">Chiama `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` per formattare il valore [Int16](xref:System.Int16) per le impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="7574e-194">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Int16](xref:System.Int16) value for the current culture.</span></span>
[<span data-ttu-id="7574e-195">Int32</span><span class="sxs-lookup"><span data-stu-id="7574e-195">Int32</span></span>](xref:System.Int32) | <span data-ttu-id="7574e-196">Chiama `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` per formattare il valore [Int32](xref:System.Int32) per le impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="7574e-196">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Int32](xref:System.Int32) value for the current culture.</span></span>
[<span data-ttu-id="7574e-197">Int64</span><span class="sxs-lookup"><span data-stu-id="7574e-197">Int64</span></span>](xref:System.Int64) | <span data-ttu-id="7574e-198">Chiama `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` per formattare il valore [Int64](xref:System.Int64) per le impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="7574e-198">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Int64](xref:System.Int64) value for the current culture.</span></span>
[<span data-ttu-id="7574e-199">SByte</span><span class="sxs-lookup"><span data-stu-id="7574e-199">SByte</span></span>](xref:System.SByte) | <span data-ttu-id="7574e-200">Chiama `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` per formattare il valore [SByte](xref:System.SByte)</span><span class="sxs-lookup"><span data-stu-id="7574e-200">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [SByte](xref:System.SByte)</span></span> | <span data-ttu-id="7574e-201">per le impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="7574e-201">value for the current culture.</span></span>
[<span data-ttu-id="7574e-202">Single</span><span class="sxs-lookup"><span data-stu-id="7574e-202">Single</span></span>](xref:System.Single) | <span data-ttu-id="7574e-203">Chiama `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` per formattare il valore [Single](xref:System.Single) per le impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="7574e-203">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Single](xref:System.Single) value for the current culture.</span></span>
[<span data-ttu-id="7574e-204">UInt32</span><span class="sxs-lookup"><span data-stu-id="7574e-204">UInt32</span></span>](xref:System.UInt32) | <span data-ttu-id="7574e-205">Chiama `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` per formattare il valore [UInt32](xref:System.UInt32) per le impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="7574e-205">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [UInt32](xref:System.UInt32)value for the current culture.</span></span>
[<span data-ttu-id="7574e-206">UInt32</span><span class="sxs-lookup"><span data-stu-id="7574e-206">UInt32</span></span>](xref:System.UInt32) | <span data-ttu-id="7574e-207">Chiama `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` per formattare il valore [UInt32](xref:System.UInt32) per le impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="7574e-207">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [UInt32](xref:System.UInt32) value for the current culture.</span></span>
[<span data-ttu-id="7574e-208">UInt64</span><span class="sxs-lookup"><span data-stu-id="7574e-208">UInt64</span></span>](xref:System.UInt64) | <span data-ttu-id="7574e-209">Chiama `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` per formattare il valore [UInt64](xref:System.UInt64) per le impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="7574e-209">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [UInt64](xref:System.UInt64)  value for the current culture.</span></span>

## <a name="the-tostring-method-and-format-strings"></a><span data-ttu-id="7574e-210">Metodo ToString e stringhe di formato</span><span class="sxs-lookup"><span data-stu-id="7574e-210">The ToString method and format strings</span></span>

<span data-ttu-id="7574e-211">L'utilizzo del metodo [ToString](xref:System.Object.ToString) predefinito o l'esecuzione dell'override di [ToString](xref:System.Object.ToString) è un'operazione appropriata quando un oggetto dispone di una singola rappresentazione di stringa.</span><span class="sxs-lookup"><span data-stu-id="7574e-211">Relying on the default [ToString](xref:System.Object.ToString) method or overriding [ToString](xref:System.Object.ToString) is appropriate when an object has a single string representation.</span></span> <span data-ttu-id="7574e-212">Spesso, tuttavia, il valore di un oggetto dispone di più rappresentazioni.</span><span class="sxs-lookup"><span data-stu-id="7574e-212">However, the value of an object often has multiple representations.</span></span> <span data-ttu-id="7574e-213">È ad esempio possibile esprimere una temperatura in gradi Fahrenheit, gradi Celsius o gradi Kelvin.</span><span class="sxs-lookup"><span data-stu-id="7574e-213">For example, a temperature can be expressed in degrees Fahrenheit, degrees Celsius, or kelvins.</span></span> <span data-ttu-id="7574e-214">Analogamente, il valore intero 10 può essere rappresentato in diversi modi, tra cui 10, 10,0, 1.0e01 o €10,00.</span><span class="sxs-lookup"><span data-stu-id="7574e-214">Similarly, the integer value 10 can be represented in numerous ways, including 10, 10.0, 1.0e01, or $10.00.</span></span>

<span data-ttu-id="7574e-215">Per consentire a un singolo valore di disporre di più rappresentazioni di stringa, in .NET vengono usate le stringhe di formato.</span><span class="sxs-lookup"><span data-stu-id="7574e-215">To enable a single value to have multiple string representations, .NET uses format strings.</span></span> <span data-ttu-id="7574e-216">Una stringa di formato è una stringa che contiene uno o più identificatori di formato predefiniti costituiti da singoli caratteri o gruppi di caratteri che definiscono il modo in cui deve essere formattato l'output del metodo [ToString](xref:System.Object.ToString).</span><span class="sxs-lookup"><span data-stu-id="7574e-216">A format string is a string that contains one or more predefined format specifiers, which are single characters or groups of characters that define how the [ToString](xref:System.Object.ToString) method should format its output.</span></span> <span data-ttu-id="7574e-217">La stringa di formato viene quindi passata come parametro al metodo [ToString](xref:System.Object.ToString) dell'oggetto per determinare come deve venire visualizzata la rappresentazione di stringa del valore di tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="7574e-217">The format string is then passed as a parameter to the object's [ToString](xref:System.Object.ToString) method and determines how the string representation of that object's value should appear.</span></span>

<span data-ttu-id="7574e-218">Tutti i tipi numerici, di data e ora e di enumerazione in .NET supportano un set predefinito di identificatori di formato.</span><span class="sxs-lookup"><span data-stu-id="7574e-218">All numeric types, date and time types, and enumeration types in .NET support a predefined set of format specifiers.</span></span> <span data-ttu-id="7574e-219">È anche possibile usare le stringhe di formato per definire più rappresentazioni di stringa dei tipi di dati definiti dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7574e-219">You can also use format strings to define multiple string representations of your application-defined data types.</span></span>

### <a name="standard-format-strings"></a><span data-ttu-id="7574e-220">Stringhe di formato standard</span><span class="sxs-lookup"><span data-stu-id="7574e-220">Standard format strings</span></span>

<span data-ttu-id="7574e-221">Una stringa di formato standard contiene un singolo identificatore di formato, che è un carattere alfabetico che definisce la rappresentazione di stringa dell'oggetto a cui viene applicata, insieme a un identificatore di precisione facoltativo, che influisce sul numero di cifre visualizzate nella stringa di risultato.</span><span class="sxs-lookup"><span data-stu-id="7574e-221">A standard format string contains a single format specifier, which is an alphabetic character that defines the string representation of the object to which it is applied, along with an optional precision specifier that affects how many digits are displayed in the result string.</span></span> <span data-ttu-id="7574e-222">Se l'identificatore di precisione viene omesso o non è supportato, un identificatore di formato standard è equivalente a una stringa di formato standard.</span><span class="sxs-lookup"><span data-stu-id="7574e-222">If the precision specifier is omitted or is not supported, a standard format specifier is equivalent to a standard format string.</span></span> 

<span data-ttu-id="7574e-223">In .NET viene definito un set di identificatori di formato standard per tutti i tipi numerici, di data e ora e di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="7574e-223">.NET defines a set of standard format specifiers for all numeric types, all date and time types, and all enumeration types.</span></span> <span data-ttu-id="7574e-224">Ognuna di queste categorie supporta, ad esempio, un identificatore di formato standard "G", che definisce una rappresentazione di stringa generale di un valore di tale tipo.</span><span class="sxs-lookup"><span data-stu-id="7574e-224">For example, each of these categories supports a "G" standard format specifier, which defines a general string representation of a value of that type.</span></span>

<span data-ttu-id="7574e-225">Le stringhe di formato standard per i tipi di enumerazione controllano direttamente la rappresentazione di stringa di un valore.</span><span class="sxs-lookup"><span data-stu-id="7574e-225">Standard format strings for enumeration types directly control the string representation of a value.</span></span> <span data-ttu-id="7574e-226">Le stringhe di formato passate al metodo [ToString](xref:System.Object.ToString) del valore di un'enumerazione determinano se il valore viene visualizzato tramite il relativo nome di stringa (identificatori di formato "G" e "F"), il relativo valore integrale sottostante (identificatore di formato "D") oppure il relativo valore esadecimale (identificatore di formato "X").</span><span class="sxs-lookup"><span data-stu-id="7574e-226">The format strings passed to an enumeration value’s [ToString](xref:System.Object.ToString) method determine whether the value is displayed using its string name (the "G" and "F" format specifiers), its underlying integral value (the "D" format specifier), or its hexadecimal value (the "X" format specifier).</span></span> <span data-ttu-id="7574e-227">Nell'esempio seguente viene illustrato l'uso delle stringhe di formato standard per formattare un valore dell'enumerazione [DayOfWeek](xref:System.DayOfWeek).</span><span class="sxs-lookup"><span data-stu-id="7574e-227">The following example illustrates the use of standard format strings to format a [DayOfWeek](xref:System.DayOfWeek) enumeration value.</span></span> 

```csharp
DayOfWeek thisDay = DayOfWeek.Monday;
string[] formatStrings = {"G", "F", "D", "X"};

foreach (string formatString in formatStrings)
   Console.WriteLine(thisDay.ToString(formatString));
// The example displays the following output:
//       Monday
//       Monday
//       1
//       00000001
```

```vb
Dim thisDay As DayOfWeek = DayOfWeek.Monday
Dim formatStrings() As String = {"G", "F", "D", "X"}

For Each formatString As String In formatStrings
   Console.WriteLine(thisDay.ToString(formatString))
Next
' The example displays the following output:
'       Monday
'       Monday
'       1
'       00000001
```

<span data-ttu-id="7574e-228">Per informazioni sulle stringhe di formato di enumerazione, vedere [Stringhe di formato di enumerazione](enumeration-format.md).</span><span class="sxs-lookup"><span data-stu-id="7574e-228">For information about enumeration format strings, see [Enumeration format strings](enumeration-format.md).</span></span>

<span data-ttu-id="7574e-229">Le stringhe di formato standard per i tipi numerici definiscono in genere una stringa di risultato il cui aspetto preciso viene controllato da uno o più valori delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="7574e-229">Standard format strings for numeric types usually define a result string whose precise appearance is controlled by one or more property values.</span></span> <span data-ttu-id="7574e-230">L'identificatore di formato "C", ad esempio, consente di formattare un numero come valore di valuta.</span><span class="sxs-lookup"><span data-stu-id="7574e-230">For example, the "C" format specifier formats a number as a currency value.</span></span> <span data-ttu-id="7574e-231">Quando si chiama il metodo [ToString](xref:System.Object.ToString) con l'identificatore di formato "C" come unico parametro, vengono usati i valori delle proprietà seguenti dell'oggetto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) delle impostazioni cultura correnti per definire la rappresentazione di stringa del valore numerico:</span><span class="sxs-lookup"><span data-stu-id="7574e-231">When you call the [ToString](xref:System.Object.ToString) method with the "C" format specifier as the only parameter, the following property values from the current culture’s [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object are used to define the string representation of the numeric value:</span></span>

* <span data-ttu-id="7574e-232">Proprietà [CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol), che specifica il simbolo di valuta delle impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="7574e-232">The [CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol) property, which specifies the current culture’s currency symbol.</span></span>

* <span data-ttu-id="7574e-233">Proprietà [CurrencyNegativePattern](xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern) o [CurrencyPositivePattern](xref:System.Globalization.NumberFormatInfo.CurrencyPositivePattern) , che restituisce un intero che determina quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7574e-233">The [CurrencyNegativePattern](xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern) or [CurrencyPositivePattern](xref:System.Globalization.NumberFormatInfo.CurrencyPositivePattern) property, which returns an integer that determines the following:</span></span> 

    * <span data-ttu-id="7574e-234">Posizione del simbolo di valuta.</span><span class="sxs-lookup"><span data-stu-id="7574e-234">The placement of the currency symbol.</span></span>
    
    * <span data-ttu-id="7574e-235">Utilizzo di un segno negativo iniziale, di un segno negativo finale o di parentesi per indicare i valori negativi.</span><span class="sxs-lookup"><span data-stu-id="7574e-235">Whether negative values are indicated by a leading negative sign, a trailing negative sign, or parentheses.</span></span>
    
    * <span data-ttu-id="7574e-236">Inserimento di uno spazio tra il valore numerico e il simbolo di valuta.</span><span class="sxs-lookup"><span data-stu-id="7574e-236">Whether a space appears between the numeric value and the currency symbol.</span></span>
    
* <span data-ttu-id="7574e-237">Proprietà [CurrencyDecimalDigits](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits), che definisce il numero di cifre frazionarie nella stringa di risultato.</span><span class="sxs-lookup"><span data-stu-id="7574e-237">The [CurrencyDecimalDigits](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits) property, which defines the number of fractional digits in the result string.</span></span>

* <span data-ttu-id="7574e-238">Proprietà [CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator), che definisce il simbolo del separatore decimale nella stringa di risultato.</span><span class="sxs-lookup"><span data-stu-id="7574e-238">The [CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator) property, which defines the decimal separator symbol in the result string.</span></span>

* <span data-ttu-id="7574e-239">Proprietà [CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator), che definisce il simbolo del separatore di gruppi.</span><span class="sxs-lookup"><span data-stu-id="7574e-239">The [CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator) property, which defines the group separator symbol.</span></span>

* <span data-ttu-id="7574e-240">Proprietà [CurrencyGroupSizes](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSizes), che definisce il numero di cifre in ogni gruppo a sinistra del separatore decimale.</span><span class="sxs-lookup"><span data-stu-id="7574e-240">The [CurrencyGroupSizes](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSizes) property, which defines the number of digits in each group to the left of the decimal.</span></span>

* <span data-ttu-id="7574e-241">Proprietà [NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign), che determina il segno negativo usato nella stringa di risultato se non vengono usate parentesi per indicare i valori negativi.</span><span class="sxs-lookup"><span data-stu-id="7574e-241">The [NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) property, which determines the negative sign used in the result string if parentheses are not used to indicate negative values.</span></span>

<span data-ttu-id="7574e-242">Le stringhe di formato numerico possono inoltre includere un identificatore di precisione.</span><span class="sxs-lookup"><span data-stu-id="7574e-242">In addition, numeric format strings may include a precision specifier.</span></span> <span data-ttu-id="7574e-243">Il significato di questo identificatore dipende dalla stringa di formato con la quale viene usato, ma in genere esso indica il numero totale di cifre o il numero di cifre frazionarie che devono essere presenti nella stringa di risultato.</span><span class="sxs-lookup"><span data-stu-id="7574e-243">The meaning of this specifier depends on the format string with which it is used, but it typically indicates either the total number of digits or the number of fractional digits that should appear in the result string.</span></span> <span data-ttu-id="7574e-244">Nell'esempio seguente vengono usati, ad esempio, la stringa numerica standard "X4"e un identificatore di precisione per creare un valore stringa con quattro cifre esadecimali.</span><span class="sxs-lookup"><span data-stu-id="7574e-244">For example, the following example uses the "X4" standard numeric string and a precision specifier to create a string value that has four hexadecimal digits.</span></span>

```csharp
byte[] byteValues = { 12, 163, 255 };
foreach (byte byteValue in byteValues)
   Console.WriteLine(byteValue.ToString("X4"));
// The example displays the following output:
//       000C
//       00A3
//       00FF
```

```vb
Dim byteValues() As Byte = { 12, 163, 255 }
For Each byteValue As Byte In byteValues
   Console.WriteLine(byteValue.ToString("X4"))
Next
' The example displays the following output:
'       000C
'       00A3
'       00FF
```

<span data-ttu-id="7574e-245">Per altre informazioni sulle stringhe di formato numerico standard, vedere [Stringhe di formato numerico standard](standard-numeric.md).</span><span class="sxs-lookup"><span data-stu-id="7574e-245">For more information about standard numeric formatting strings, see [Standard numeric format strings](standard-numeric.md).</span></span> 

<span data-ttu-id="7574e-246">Le stringhe di formato standard per i valori di data e ora sono alias per stringhe di formato personalizzate archiviate da una proprietà [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) specifica.</span><span class="sxs-lookup"><span data-stu-id="7574e-246">Standard format strings for date and time values are aliases for custom format strings stored by a particular [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) class.</span></span> <span data-ttu-id="7574e-247">Se viene chiamato, ad esempio, il metodo [ToString](xref:System.Object.ToString) di un valore di data e ora con l'identificatore di formato "D", la data e l'ora vengono visualizzate usando la stringa di formato personalizzata archiviata nella proprietà [DateTimeFormatInfo.LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern) delle impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="7574e-247">For example, calling the [ToString](xref:System.Object.ToString) method of a date and time value with the "D" format specifier displays the date and time by using the custom format string stored in the current culture’s [DateTimeFormatInfo.LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern) property.</span></span> <span data-ttu-id="7574e-248">Per altre informazioni sulle stringhe di formato personalizzate, vedere la sezione [Stringhe di formato personalizzate](#custom-format-strings). Nell'esempio seguente viene illustrata questa relazione.</span><span class="sxs-lookup"><span data-stu-id="7574e-248">(For more information about custom format strings, see the [Custom format strings](#custom-format-strings) section.) The following example illustrates this relationship.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      DateTime date1 = new DateTime(2017, 6, 30);
      Console.WriteLine("D Format Specifier:     {0:D}", date1);
      string longPattern = CultureInfo.CurrentCulture.DateTimeFormat.LongDatePattern;
      Console.WriteLine("'{0}' custom format string:     {1}", 
                        longPattern, date1.ToString(longPattern));
   }
}
// The example displays the following output when run on a system whose
// current culture is en-US:
//    D Format Specifier:     Tuesday, June 30, 2017
//    'dddd, MMMM dd, yyyy' custom format string:     Tuesday, June 30, 2017
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim date1 As Date = #6/30/2009#
      Console.WriteLine("D Format Specifier:     {0:D}", date1)
      Dim longPattern As String = CultureInfo.CurrentCulture.DateTimeFormat.LongDatePattern
      Console.WriteLine("'{0}' custom format string:     {1}", _
                        longPattern, date1.ToString(longPattern))
   End Sub
End Module
' The example displays the following output when run on a system whose
' current culture is en-US:
'    D Format Specifier:     Tuesday, June 30, 2009
'    'dddd, MMMM dd, yyyy' custom format string:     Tuesday, June 30, 2009
```

<span data-ttu-id="7574e-249">Per altre informazioni sulle stringhe di formato di data e ora standard, vedere [Stringhe di formato di data e ora standard](standard-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="7574e-249">For more information about standard date and time format strings, see [Standard date and time format strings](standard-datetime.md).</span></span>

<span data-ttu-id="7574e-250">È anche possibile usare le stringhe di formato standard per definire la rappresentazione di stringa di un oggetto definito dall'applicazione, prodotta dal metodo `ToString(String)` dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7574e-250">You can also use standard format strings to define the string representation of an application-defined object that is produced by the object’s `ToString(String)` method.</span></span> <span data-ttu-id="7574e-251">È possibile definire gli identificatori di formato standard specifici supportati dall'oggetto, nonché determinare se per essi viene fatta o meno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="7574e-251">You can define the specific standard format specifiers that your object supports, and you can determine whether they are case-sensitive or case-insensitive.</span></span> <span data-ttu-id="7574e-252">L'implementazione del metodo `ToString(String)` deve supportare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7574e-252">Your implementation of the `ToString(String)` method should support the following:</span></span>

* <span data-ttu-id="7574e-253">Un identificatore di formato "G" che rappresenta un formato abituale o comune dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7574e-253">A "G" format specifier that represents a customary or common format of the object.</span></span> <span data-ttu-id="7574e-254">L'overload senza parametri del metodo `ToString` dell'oggetto deve chiamare il relativo overload di `ToString(String)` e passare a esso la stringa di formato standard "G".</span><span class="sxs-lookup"><span data-stu-id="7574e-254">The parameterless overload of your object's `ToString` method should call its `ToString(String)` overload and pass it the "G" standard format string.</span></span>

* <span data-ttu-id="7574e-255">Supporto per un identificatore di formato equivalente a un riferimento Null.</span><span class="sxs-lookup"><span data-stu-id="7574e-255">Support for a format specifier that is equal to a null reference.</span></span> <span data-ttu-id="7574e-256">Un identificatore di formato equivalente a un riferimento Null deve essere considerato equivalente all'identificatore di formato "G".</span><span class="sxs-lookup"><span data-stu-id="7574e-256">A format specifier that is equal to a null reference should be considered equivalent to the "G" format specifier.</span></span>

<span data-ttu-id="7574e-257">Una classe `Temperature` può, ad esempio, archiviare internamente la temperatura in gradi Celsius e usare gli identificatori di formato per rappresentare il valore dell'oggetto `Temperature` in gradi Celsius, gradi Fahrenheit e gradi Kelvin.</span><span class="sxs-lookup"><span data-stu-id="7574e-257">For example, a `Temperature` class can internally store the temperature in degrees Celsius and use format specifiers to represent the value of the `Temperature` object in degrees Celsius, degrees Fahrenheit, and kelvins.</span></span> <span data-ttu-id="7574e-258">Nell'esempio seguente viene illustrato questo concetto.</span><span class="sxs-lookup"><span data-stu-id="7574e-258">The following example provides an illustration.</span></span>

```csharp
using System;

public class Temperature
{
   private decimal m_Temp;

   public Temperature(decimal temperature)
   {
      this.m_Temp = temperature;
   }

   public decimal Celsius
   {
      get { return this.m_Temp; }
   }

   public decimal Kelvin
   {
      get { return this.m_Temp + 273.15m; }   
   }

   public decimal Fahrenheit
   {
      get { return Math.Round(((decimal) (this.m_Temp * 9 / 5 + 32)), 2); }
   }

   public override string ToString()
   {
      return this.ToString("C");
   }

   public string ToString(string format)
   {  
      // Handle null or empty string.
      if (String.IsNullOrEmpty(format)) format = "C";
      // Remove spaces and convert to uppercase.
      format = format.Trim().ToUpperInvariant();      

      // Convert temperature to Fahrenheit and return string.
      switch (format)
      {
         // Convert temperature to Fahrenheit and return string.
         case "F":
            return this.Fahrenheit.ToString("N2") + " °F";
         // Convert temperature to Kelvin and return string.
         case "K":
            return this.Kelvin.ToString("N2") + " K";
         // return temperature in Celsius.
         case "G":
         case "C":
            return this.Celsius.ToString("N2") + " °C";
         default:
            throw new FormatException(String.Format("The '{0}' format string is not supported.", format));
      }      
   }
}

public class Example
{
   public static void Main()
   {
      Temperature temp1 = new Temperature(0m);
      Console.WriteLine(temp1.ToString());
      Console.WriteLine(temp1.ToString("G"));
      Console.WriteLine(temp1.ToString("C"));
      Console.WriteLine(temp1.ToString("F"));
      Console.WriteLine(temp1.ToString("K"));

      Temperature temp2 = new Temperature(-40m);
      Console.WriteLine(temp2.ToString());
      Console.WriteLine(temp2.ToString("G"));
      Console.WriteLine(temp2.ToString("C"));
      Console.WriteLine(temp2.ToString("F"));
      Console.WriteLine(temp2.ToString("K"));

      Temperature temp3 = new Temperature(16m);
      Console.WriteLine(temp3.ToString());
      Console.WriteLine(temp3.ToString("G"));
      Console.WriteLine(temp3.ToString("C"));
      Console.WriteLine(temp3.ToString("F"));
      Console.WriteLine(temp3.ToString("K"));

      Console.WriteLine(String.Format("The temperature is now {0:F}.", temp3));
   }
}
// The example displays the following output:
//       0.00 °C
//       0.00 °C
//       0.00 °C
//       32.00 °F
//       273.15 K
//       -40.00 °C
//       -40.00 °C
//       -40.00 °C
//       -40.00 °F
//       233.15 K
//       16.00 °C
//       16.00 °C
//       16.00 °C
//       60.80 °F
//       289.15 K
//       The temperature is now 16.00 °C.
```

```vb
Public Class Temperature
   Private m_Temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.m_Temp = temperature
   End Sub

   Public ReadOnly Property Celsius() As Decimal
      Get
         Return Me.m_Temp
      End Get   
   End Property

   Public ReadOnly Property Kelvin() As Decimal
      Get
         Return Me.m_Temp + 273.15d   
      End Get
   End Property

   Public ReadOnly Property Fahrenheit() As Decimal
      Get
         Return Math.Round(CDec(Me.m_Temp * 9 / 5 + 32), 2)
      End Get      
   End Property

   Public Overrides Function ToString() As String
      Return Me.ToString("C")
   End Function

   Public Overloads Function ToString(format As String) As String  
      ' Handle null or empty string.
      If String.IsNullOrEmpty(format) Then format = "C"
      ' Remove spaces and convert to uppercase.
      format = format.Trim().ToUpperInvariant()      

      Select Case format
         Case "F"
           ' Convert temperature to Fahrenheit and return string.
            Return Me.Fahrenheit.ToString("N2") & " °F"
         Case "K"
            ' Convert temperature to Kelvin and return string.
            Return Me.Kelvin.ToString("N2") & " K"
         Case "C", "G"
            ' Return temperature in Celsius.
            Return Me.Celsius.ToString("N2") & " °C"
         Case Else
            Throw New FormatException(String.Format("The '{0}' format string is not supported.", format))
      End Select      
   End Function
End Class

Public Module Example
   Public Sub Main()
      Dim temp1 As New Temperature(0d)
      Console.WriteLine(temp1.ToString())
      Console.WriteLine(temp1.ToString("G"))
      Console.WriteLine(temp1.ToString("C"))
      Console.WriteLine(temp1.ToString("F"))
      Console.WriteLine(temp1.ToString("K"))

      Dim temp2 As New Temperature(-40d)
      Console.WriteLine(temp2.ToString())
      Console.WriteLine(temp2.ToString("G"))
      Console.WriteLine(temp2.ToString("C"))
      Console.WriteLine(temp2.ToString("F"))
      Console.WriteLine(temp2.ToString("K"))

      Dim temp3 As New Temperature(16d)
      Console.WriteLine(temp3.ToString())
      Console.WriteLine(temp3.ToString("G"))
      Console.WriteLine(temp3.ToString("C"))
      Console.WriteLine(temp3.ToString("F"))
      Console.WriteLine(temp3.ToString("K"))

      Console.WriteLine(String.Format("The temperature is now {0:F}.", temp3))
   End Sub
End Module
' The example displays the following output:
'       0.00 °C
'       0.00 °C
'       0.00 °C
'       32.00 °F
'       273.15 K
'       -40.00 °C
'       -40.00 °C
'       -40.00 °C
'       -40.00 °F
'       233.15 K
'       16.00 °C
'       16.00 °C
'       16.00 °C
'       60.80 °F
'       289.15 K
'       The temperature is now 16.00 °C.
```

### <a name="custom-format-strings"></a><span data-ttu-id="7574e-259">Stringhe di formato personalizzate</span><span class="sxs-lookup"><span data-stu-id="7574e-259">Custom format strings</span></span>

<span data-ttu-id="7574e-260">Oltre alle stringhe di formato standard, in .NET sono definite stringhe di formato personalizzate sia per valori numerici che per valori di data e ora.</span><span class="sxs-lookup"><span data-stu-id="7574e-260">In addition to the standard format strings, .NET defines custom format strings for both numeric values and date and time values.</span></span> <span data-ttu-id="7574e-261">Una stringa di formato personalizzata è costituita da uno o più identificatori di formato personalizzati che definiscono la rappresentazione di stringa di un valore.</span><span class="sxs-lookup"><span data-stu-id="7574e-261">A custom format string consists of one or more custom format specifiers that define the string representation of a value.</span></span> <span data-ttu-id="7574e-262">La stringa di formato di data e ora personalizzata "yyyy/mm/dd hh:mm:ss.ffff t zzz" consente, ad esempio, di convertire una data nella relativa rappresentazione di stringa nel formato "2008/11/15 07:45:00.0000 P -08:00" per le impostazioni cultura en-US.</span><span class="sxs-lookup"><span data-stu-id="7574e-262">For example, the custom date and time format string "yyyy/mm/dd hh:mm:ss.ffff t zzz" converts a date to its string representation in the form "2008/11/15 07:45:00.0000 P -08:00" for the en-US culture.</span></span> <span data-ttu-id="7574e-263">Analogamente, la stringa di formato personalizzata "0000" consente di convertire il valore intero 12 in "0012".</span><span class="sxs-lookup"><span data-stu-id="7574e-263">Similarly, the custom format string "0000" converts the integer value 12 to "0012".</span></span> <span data-ttu-id="7574e-264">Per un elenco completo di stringhe di formato personalizzate, vedere [Stringhe di formato di data e ora personalizzate](custom-datetime.md) e [Stringhe di formato numerico personalizzate](custom-numeric.md).</span><span class="sxs-lookup"><span data-stu-id="7574e-264">For a complete list of custom format strings, see [Custom date and time format strings](custom-datetime.md) and [Custom numeric format strings](custom-numeric.md).</span></span>

<span data-ttu-id="7574e-265">Se una stringa di formato è costituita da un solo identificatore di formato personalizzato, l'identificatore di formato deve essere preceduto dal simbolo di percentuale (%) per evitare confusione con un identificatore di formato standard.</span><span class="sxs-lookup"><span data-stu-id="7574e-265">If a format string consists of a single custom format specifier, the format specifier should be preceded by the percent (%) symbol to avoid confusion with a standard format specifier.</span></span> <span data-ttu-id="7574e-266">Nell'esempio seguente viene usato l'identificatore di formato personalizzato "M" per visualizzare un numero a una cifra o a due cifre del mese di una data specifica.</span><span class="sxs-lookup"><span data-stu-id="7574e-266">The following example uses the "M" custom format specifier to display a one-digit or two-digit number of the month of a particular date.</span></span>

```csharp
DateTime date1 = new DateTime(2009, 9, 8);
Console.WriteLine(date1.ToString("%M"));       
// Displays 9
```

```vb
Dim date1 As Date = #09/08/2009#
Console.WriteLine(date1.ToString("%M"))      ' Displays 9
```

<span data-ttu-id="7574e-267">Numerose stringhe di formato standard per i valori di data e ora sono alias per stringhe di formato personalizzate definite dalle proprietà dell'oggetto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo).</span><span class="sxs-lookup"><span data-stu-id="7574e-267">Many standard format strings for date and time values are aliases for custom format strings that are defined by properties of the [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object.</span></span> <span data-ttu-id="7574e-268">Le stringhe di formato personalizzate offrono inoltre una notevole flessibilità in quanto consentono una formattazione definita dall'applicazione per valori numerici o di data e ora.</span><span class="sxs-lookup"><span data-stu-id="7574e-268">Custom format strings also offer considerable flexibility in providing application-defined formatting for numeric values or date and time values.</span></span> <span data-ttu-id="7574e-269">È possibile definire stringhe di risultato personalizzate sia per valori numerici che per valori di data e ora combinando più identificatori di formato personalizzati in una singola stringa di formato personalizzata.</span><span class="sxs-lookup"><span data-stu-id="7574e-269">You can define your own custom result strings for both numeric values and date and time values by combining multiple custom format specifiers into a single custom format string.</span></span> <span data-ttu-id="7574e-270">Nell'esempio seguente viene definita una stringa di formato personalizzata che consente di visualizzare il giorno della settimana tra parentesi dopo il nome del mese, il giorno e l'anno.</span><span class="sxs-lookup"><span data-stu-id="7574e-270">The following example defines a custom format string that displays the day of the week in parentheses after the month name, day, and year.</span></span>

```csharp
string customFormat = "MMMM dd, yyyy (dddd)";
DateTime date1 = new DateTime(2009, 8, 28);
Console.WriteLine(date1.ToString(customFormat));   
// The example displays the following output if run on a system
// whose language is English:
//       August 28, 2009 (Friday) 
```

```vb
Dim customFormat As String = "MMMM dd, yyyy (dddd)"
Dim date1 As Date = #8/28/2009#
Console.WriteLine(date1.ToString(customFormat))   
' The example displays the following output if run on a system
' whose language is English:
'       August 28, 2009 (Friday) 
```

<span data-ttu-id="7574e-271">L'esempio seguente definisce una stringa di formato personalizzata che visualizza un valore [Int64](xref:System.Int64) come numero di telefono degli Stati Uniti standard di sette cifre con il relativo prefisso.</span><span class="sxs-lookup"><span data-stu-id="7574e-271">The following example defines a custom format string that displays an [Int64](xref:System.Int64) value as a standard, seven-digit U.S. telephone number along with its area code.</span></span> 

```csharp
using System;

public class Example
{
   public static void Main()
   {
      long number = 8009999999;
      string fmt = "000-000-0000";
      Console.WriteLine(number.ToString(fmt));
   }
}
// The example displays the following output:
//        800-999-9999
```

```vb
Module Example
   Public Sub Main()
      Dim number As Long = 8009999999
      Dim fmt As String = "000-000-0000"
      Console.WriteLine(number.ToString(fmt))
   End Sub
End Module
' The example displays the following output:

' The example displays the following output:
'       800-999-9999
```

<span data-ttu-id="7574e-272">Sebbene le stringhe di formato standard consentano in genere di gestire la maggior parte delle necessità relative alla formattazione per i tipi definiti dall'applicazione, è anche possibile definire identificatori di formato personalizzati per formattare i tipi.</span><span class="sxs-lookup"><span data-stu-id="7574e-272">Although standard format strings can generally handle most of the formatting needs for your application-defined types, you may also define custom format specifiers to format your types.</span></span> 

### <a name="format-strings-and-net-types"></a><span data-ttu-id="7574e-273">Stringhe di formato e tipi .NET</span><span class="sxs-lookup"><span data-stu-id="7574e-273">Format strings and .NET types</span></span>

<span data-ttu-id="7574e-274">Tutti i tipi numerici, ovvero[Byte](xref:System.Byte), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64) e [BigInteger](xref:System.Numerics.BigInteger), e i tipi [DateTime](xref:System.DateTime), [DateTimeOffset](xref:System.DateTimeOffset), [TimeSpan](xref:System.TimeSpan), [Guid](xref:System.Guid) e tutti i tipi di enumerazione supportano la formattazione con stringhe di formato.</span><span class="sxs-lookup"><span data-stu-id="7574e-274">All numeric types (that is, the [Byte](xref:System.Byte), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64), and [BigInteger](xref:System.Numerics.BigInteger) types), as well as the [DateTime](xref:System.DateTime), [DateTimeOffset](xref:System.DateTimeOffset), [TimeSpan](xref:System.TimeSpan), [Guid](xref:System.Guid), and all enumeration types, support formatting with format strings.</span></span> <span data-ttu-id="7574e-275">Per informazioni sulle stringhe di formato specifiche supportate da ogni tipo, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7574e-275">For information on the specific format strings supported by each type, see the following topics:</span></span> 

<span data-ttu-id="7574e-276">Titolo</span><span class="sxs-lookup"><span data-stu-id="7574e-276">Title</span></span> | <span data-ttu-id="7574e-277">Definizione</span><span class="sxs-lookup"><span data-stu-id="7574e-277">Definition</span></span>
----- | ----------
[<span data-ttu-id="7574e-278">Stringhe di formato numerico standard</span><span class="sxs-lookup"><span data-stu-id="7574e-278">Standard numeric format strings</span></span>](standard-numeric.md) | <span data-ttu-id="7574e-279">Vengono descritte le stringhe di formato standard che consentono di creare rappresentazioni di stringa usate comunemente di valori numerici.</span><span class="sxs-lookup"><span data-stu-id="7574e-279">Describes standard format strings that create commonly used string representations of numeric values.</span></span> 
[<span data-ttu-id="7574e-280">Stringhe di formato numerico personalizzato</span><span class="sxs-lookup"><span data-stu-id="7574e-280">Custom numeric format strings</span></span>](custom-numeric.md) | <span data-ttu-id="7574e-281">Vengono descritte le stringhe di formato personalizzate che consentono di creare formati specifici dell'applicazione per valori numerici.</span><span class="sxs-lookup"><span data-stu-id="7574e-281">Describes custom format strings that create application-specific formats for numeric values.</span></span>
[<span data-ttu-id="7574e-282">Stringhe di formato di data e ora standard</span><span class="sxs-lookup"><span data-stu-id="7574e-282">Standard date and time format strings</span></span>](standard-datetime.md) | <span data-ttu-id="7574e-283">Vengono descritte le stringhe di formato standard che consentono di creare rappresentazioni di stringa usate comunemente di valori [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="7574e-283">Describes standard format strings that create commonly used string representations of [DateTime](xref:System.DateTime) values.</span></span>
[<span data-ttu-id="7574e-284">Stringhe di formato di data e ora personalizzato</span><span class="sxs-lookup"><span data-stu-id="7574e-284">Custom date and time format strings</span></span>](custom-datetime.md) | <span data-ttu-id="7574e-285">Vengono descritte le stringhe di formato personalizzate che consentono di creare formati specifici dell'applicazione per valori [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="7574e-285">Describes custom format strings that create application-specific formats for [DateTime](xref:System.DateTime) values.</span></span>
[<span data-ttu-id="7574e-286">Stringhe di formato TimeSpan standard</span><span class="sxs-lookup"><span data-stu-id="7574e-286">Standard TimeSpan format Strings</span></span>](standard-timespan.md) | <span data-ttu-id="7574e-287">Vengono descritte le stringhe di formato standard che consentono di creare rappresentazioni di stringa usate comunemente di intervalli di tempo.</span><span class="sxs-lookup"><span data-stu-id="7574e-287">Describes standard format strings that create commonly used string representations of time intervals.</span></span>
[<span data-ttu-id="7574e-288">Stringhe di formato TimeSpan personalizzate</span><span class="sxs-lookup"><span data-stu-id="7574e-288">Custom TimeSpan format strings</span></span>](custom-timespan.md) | <span data-ttu-id="7574e-289">Vengono descritte le stringhe di formato personalizzate che consentono di creare formati specifici dell'applicazione per intervalli di tempo.</span><span class="sxs-lookup"><span data-stu-id="7574e-289">Describes custom format strings that create application-specific formats for time intervals.</span></span>
[<span data-ttu-id="7574e-290">Stringhe di formato di enumerazione</span><span class="sxs-lookup"><span data-stu-id="7574e-290">Enumeration format strings</span></span>](enumeration-format.md) | <span data-ttu-id="7574e-291">Vengono descritte le stringhe di formato standard che consentono di creare rappresentazioni di stringa di valori di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="7574e-291">Describes standard format strings that are used to create string representations of enumeration values.</span></span>
<span data-ttu-id="7574e-292">[Guid.ToString(String)](xref:System.Guid.ToString(System.String))</span><span class="sxs-lookup"><span data-stu-id="7574e-292">[Guid.ToString(String)](xref:System.Guid.ToString(System.String))</span></span> | <span data-ttu-id="7574e-293">Descrive le stringhe di formato standard per i valori [Guid](xref:System.Guid).</span><span class="sxs-lookup"><span data-stu-id="7574e-293">Describes standard format strings for [Guid](xref:System.Guid) values.</span></span>

## <a name="culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface"></a><span data-ttu-id="7574e-294">Formattazione dipendente dalle impostazioni cultura con provider di formato e l'interfaccia IFormatProvider</span><span class="sxs-lookup"><span data-stu-id="7574e-294">Culture-Sensitive Formatting with Format Providers and the IFormatProvider Interface</span></span>

<span data-ttu-id="7574e-295">Sebbene gli identificatori di formato consentano di personalizzare la formattazione degli oggetti, la creazione di una rappresentazione di stringa significativa degli oggetti richiede spesso informazioni aggiuntive sulla formattazione.</span><span class="sxs-lookup"><span data-stu-id="7574e-295">Although format specifiers let you customize the formatting of objects, producing a meaningful string representation of objects often requires additional formatting information.</span></span> <span data-ttu-id="7574e-296">La formattazione, ad esempio, di un numero come valore di valuta tramite la stringa di formato standard "C" o una stringa di formato personalizzata, come ad esempio "$ #,#.00", richiede almeno la possibilità di includere nella stringa formattata le informazioni relative al simbolo di valuta, al separatore di gruppi e al separatore decimale corretti.</span><span class="sxs-lookup"><span data-stu-id="7574e-296">For example, formatting a number as a currency value by using either the "C" standard format string or a custom format string such as "$ #,#.00" requires, at a minimum, information about the correct currency symbol, group separator, and decimal separator to be available to include in the formatted string.</span></span> <span data-ttu-id="7574e-297">In .NET queste informazioni aggiuntive sulla formattazione vengono rese disponibili tramite l'interfaccia [IFormatProvider](xref:System.IFormatProvider), fornita come parametro di uno o più overload del metodo `ToString` di tipi numerici e di data e ora.</span><span class="sxs-lookup"><span data-stu-id="7574e-297">In .NET, this additional formatting information is made available through the [IFormatProvider](xref:System.IFormatProvider) interface, which is provided as a parameter to one or more overloads of the `ToString` method of numeric types and date and time types.</span></span> <span data-ttu-id="7574e-298">Le implementazioni di [IFormatProvider](xref:System.IFormatProvider) vengono usate in .NET per supportare la formattazione specifica delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="7574e-298">[IFormatProvider](xref:System.IFormatProvider) implementations are used in .NET to support culture-specific formatting.</span></span> <span data-ttu-id="7574e-299">Nell'esempio seguente viene illustrato come cambia la rappresentazione di stringa di un oggetto quando viene formattata con tre oggetti [IFormatProvider](xref:System.IFormatProvider) che rappresentano impostazioni cultura diverse.</span><span class="sxs-lookup"><span data-stu-id="7574e-299">The following example illustrates how the string representation of an object changes when it is formatted with three [IFormatProvider](xref:System.IFormatProvider) objects that represent different cultures.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      decimal value = 1603.42m;
      Console.WriteLine(value.ToString("C3", new CultureInfo("en-US")));
      Console.WriteLine(value.ToString("C3", new CultureInfo("fr-FR")));
      Console.WriteLine(value.ToString("C3", new CultureInfo("de-DE")));
   }
}
// The example displays the following output:
//       $1,603.420
//       1 603,420 €
//       1.603,420 €
```

```vb
Imports System.Globalization

Public Module Example
   Public Sub Main()
      Dim value As Decimal = 1603.42d
      Console.WriteLine(value.ToString("C3", New CultureInfo("en-US")))
      Console.WriteLine(value.ToString("C3", New CultureInfo("fr-FR")))
      Console.WriteLine(value.ToString("C3", New CultureInfo("de-DE")))
   End Sub
End Module
' The example displays the following output:
'       $1,603.420
'       1 603,420 €
'       1.603,420 €
```

<span data-ttu-id="7574e-300">L'interfaccia [IFormatProvider](xref:System.IFormatProvider) include un solo metodo, ovvero [GetFormat(Type)](xref:System.IFormatProvider.GetFormat(System.Type)), che dispone di un singolo parametro che specifica il tipo di oggetto che fornisce informazioni sulla formattazione.</span><span class="sxs-lookup"><span data-stu-id="7574e-300">The [IFormatProvider](xref:System.IFormatProvider) interface includes one method, [GetFormat(Type)](xref:System.IFormatProvider.GetFormat(System.Type)), which has a single parameter that specifies the type of object that provides formatting information.</span></span> <span data-ttu-id="7574e-301">Se il metodo può fornire un oggetto di tale tipo, lo restituisce.</span><span class="sxs-lookup"><span data-stu-id="7574e-301">If the method can provide an object of that type, it returns it.</span></span> <span data-ttu-id="7574e-302">In caso contrario, restituisce un riferimento Null.</span><span class="sxs-lookup"><span data-stu-id="7574e-302">Otherwise, it returns a null reference.</span></span>

<span data-ttu-id="7574e-303">[IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) è un metodo di callback.</span><span class="sxs-lookup"><span data-stu-id="7574e-303">[IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) is a callback method.</span></span> <span data-ttu-id="7574e-304">Quando si chiama un overload del metodo `ToString` che include un parametro [IFormatProvider](xref:System.IFormatProvider), viene chiamato il metodo [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) dell'oggetto [IFormatProvider](xref:System.IFormatProvider).</span><span class="sxs-lookup"><span data-stu-id="7574e-304">When you call a `ToString` method overload that includes an [IFormatProvider](xref:System.IFormatProvider) parameter, it calls the [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) method of that [IFormatProvider](xref:System.IFormatProvider) object.</span></span> <span data-ttu-id="7574e-305">Il metodo [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) è responsabile della restituzione di un oggetto che fornisce le informazioni sulla formattazione necessarie, specificate dal relativo parametro *formatType*, al metodo `ToString`.</span><span class="sxs-lookup"><span data-stu-id="7574e-305">The [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) method is responsible for returning an object that provides the necessary formatting information, as specified by its *formatType* parameter, to the `ToString` method.</span></span> 

<span data-ttu-id="7574e-306">Diversi metodi di conversione di stringhe o di formattazione includono un parametro di tipo [IFormatProvider](xref:System.IFormatProvider), ma in molti casi il valore del parametro viene ignorato quando il metodo viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="7574e-306">A number of formatting or string conversion methods include a parameter of type [IFormatProvider](xref:System.IFormatProvider), but in many cases the value of the parameter is ignored when the method is called.</span></span> <span data-ttu-id="7574e-307">Nella tabella seguente sono elencati alcuni dei metodi di formattazione che usano il parametro e il tipo dell'oggetto [Type](xref:System.Type) che passano al metodo [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)).</span><span class="sxs-lookup"><span data-stu-id="7574e-307">The following table lists some of the formatting methods that use the parameter and the type of the [Type](xref:System.Type) object that they pass to the [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) method.</span></span> 

<span data-ttu-id="7574e-308">Metodo</span><span class="sxs-lookup"><span data-stu-id="7574e-308">Method</span></span> | <span data-ttu-id="7574e-309">Tipo di parametro *formatType*</span><span class="sxs-lookup"><span data-stu-id="7574e-309">Type of *formatType* parameter</span></span>
------ | ------------------------------
<span data-ttu-id="7574e-310">Metodo `ToString` di tipi numerici</span><span class="sxs-lookup"><span data-stu-id="7574e-310">`ToString` method of numeric types</span></span> | [<span data-ttu-id="7574e-311">System.Globalization.NumberFormatInfo</span><span class="sxs-lookup"><span data-stu-id="7574e-311">System.Globalization.NumberFormatInfo</span></span>](xref:System.Globalization.NumberFormatInfo)
<span data-ttu-id="7574e-312">Metodo `ToString` di tipi di data e ora</span><span class="sxs-lookup"><span data-stu-id="7574e-312">`ToString` method of date and time types</span></span> | [<span data-ttu-id="7574e-313">System.Globalization.DateTimeFormatInfo</span><span class="sxs-lookup"><span data-stu-id="7574e-313">System.Globalization.DateTimeFormatInfo</span></span>](xref:System.Globalization.DateTimeFormatInfo)
<span data-ttu-id="7574e-314">[String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))</span><span class="sxs-lookup"><span data-stu-id="7574e-314">[String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))</span></span> | [<span data-ttu-id="7574e-315">System.ICustomFormatter</span><span class="sxs-lookup"><span data-stu-id="7574e-315">System.ICustomFormatter</span></span>](xref:System.ICustomFormatter)
<span data-ttu-id="7574e-316">[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))</span><span class="sxs-lookup"><span data-stu-id="7574e-316">[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))</span></span> | [<span data-ttu-id="7574e-317">System.ICustomFormatter</span><span class="sxs-lookup"><span data-stu-id="7574e-317">System.ICustomFormatter</span></span>](xref:System.ICustomFormatter)

<span data-ttu-id="7574e-318">In .NET sono disponibili tre classi che implementano [IFormatProvider](xref:System.IFormatProvider):</span><span class="sxs-lookup"><span data-stu-id="7574e-318">.NET provides three classes that implement [IFormatProvider](xref:System.IFormatProvider):</span></span> 

* <span data-ttu-id="7574e-319">[DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), una classe che offre informazioni sulla formattazione per i valori di data e ora per impostazioni cultura specifiche.</span><span class="sxs-lookup"><span data-stu-id="7574e-319">[DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), a class that provides formatting information for date and time values for a specific culture.</span></span> <span data-ttu-id="7574e-320">L'implementazione [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) relativa restituisce un'istanza di se stessa.</span><span class="sxs-lookup"><span data-stu-id="7574e-320">Its [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) implementation returns an instance of itself.</span></span>

* <span data-ttu-id="7574e-321">[NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), una classe che offre informazioni sulla formattazione numerica per impostazioni cultura specifiche.</span><span class="sxs-lookup"><span data-stu-id="7574e-321">[NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), a class that provides numeric formatting information for a specific culture.</span></span> <span data-ttu-id="7574e-322">L'implementazione [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) relativa restituisce un'istanza di se stessa.</span><span class="sxs-lookup"><span data-stu-id="7574e-322">Its [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) implementation returns an instance of itself.</span></span>

* <span data-ttu-id="7574e-323">[CultureInfo](xref:System.Globalization.CultureInfo).</span><span class="sxs-lookup"><span data-stu-id="7574e-323">[CultureInfo](xref:System.Globalization.CultureInfo).</span></span> <span data-ttu-id="7574e-324">L'implementazione [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) può restituire un oggetto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) per offrire informazioni sulla formattazione numerica o un oggetto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) per offrire informazioni sulla formattazione per i valori di data e ora.</span><span class="sxs-lookup"><span data-stu-id="7574e-324">Its [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) implementation can return either a [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object to provide numeric formatting information or a [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object to provide formatting information for date and time values.</span></span> 

<span data-ttu-id="7574e-325">È anche possibile implementare un provider di formato personalizzato per sostituire una di queste classi.</span><span class="sxs-lookup"><span data-stu-id="7574e-325">You can also implement your own format provider to replace any one of these classes.</span></span> <span data-ttu-id="7574e-326">Il metodo `GetFormat` dell'implementazione, tuttavia, deve restituire un oggetto del tipo elencato nella tabella precedente, se deve fornire informazioni sulla formattazione al metodo `ToString`.</span><span class="sxs-lookup"><span data-stu-id="7574e-326">However, your implementation’s `GetFormat` method must return an object of the type listed in the previous table if it has to provide formatting information to the `ToString` method.</span></span>

### <a name="culture-sensitive-formatting-of-numeric-values"></a><span data-ttu-id="7574e-327">Formattazione dipendente dalle impostazioni cultura di valori numerici</span><span class="sxs-lookup"><span data-stu-id="7574e-327">Culture-sensitive formatting of numeric values</span></span>

<span data-ttu-id="7574e-328">Per impostazione predefinita, la formattazione di valori numerici è dipendente dalle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="7574e-328">By default, the formatting of numeric values is culture-sensitive.</span></span> <span data-ttu-id="7574e-329">Se non si specificano impostazioni cultura quando si chiama un metodo di formattazione, vengono usate le convenzioni di formattazione delle impostazioni cultura del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="7574e-329">If you do not specify a culture when you call a formatting method, the formatting conventions of the current thread culture are used.</span></span> <span data-ttu-id="7574e-330">Questa situazione viene illustrata nell'esempio seguente in cui le impostazioni cultura del thread corrente vengono modificate quattro volte e viene chiamato il metodo [Decimal.ToString(String)](xref:System.Decimal.ToString(System.String)).</span><span class="sxs-lookup"><span data-stu-id="7574e-330">This is illustrated in the following example, which changes the current thread culture four times and then calls the [Decimal.ToString(String)](xref:System.Decimal.ToString(System.String)) method.</span></span> <span data-ttu-id="7574e-331">In ogni caso, la stringa risultante riflette le convenzioni di formattazione delle impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="7574e-331">In each case, the result string reflects the formatting conventions of the current culture.</span></span> <span data-ttu-id="7574e-332">Questo accade perché i metodi `ToString` e `ToString(String)` eseguono il wrapping di chiamate al metodo `ToString(String, IFormatProvider)` di ogni tipo numerico.</span><span class="sxs-lookup"><span data-stu-id="7574e-332">This is because the `ToString` and `ToString(String)` methods wrap calls to each numeric type's `ToString(String, IFormatProvider)` method.</span></span> 

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] cultureNames = { "en-US", "fr-FR", "es-MX", "de-DE" };
      Decimal value = 1043.17m;

      foreach (var cultureName in cultureNames) {
         // Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName);
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name);
         Console.WriteLine(value.ToString("C2"));
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//       The current culture is en-US
//       $1,043.17
//       
//       The current culture is fr-FR
//       1 043,17 €
//       
//       The current culture is es-MX
//       $1,043.17
//       
//       The current culture is de-DE
//       1.043,17 €
```

```vb
Imports System.Globalization
Imports System.Threading 

Module Example
   Public Sub Main()
      Dim cultureNames() As String = { "en-US", "fr-FR", "es-MX", "de-DE" }
      Dim value As Decimal = 1043.17d 

      For Each cultureName In cultureNames
         ' Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName)
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name)
         Console.WriteLine(value.ToString("C2"))
         Console.WriteLine()
      Next                  
   End Sub
End Module
' The example displays the following output:
'       The current culture is en-US
'       $1,043.17
'       
'       The current culture is fr-FR
'       1 043,17 €
'       
'       The current culture is es-MX
'       $1,043.17
'       
'       The current culture is de-DE
'       1.043,17 €
```

<span data-ttu-id="7574e-333">È anche possibile formattare un valore numerico per impostazioni cultura specifiche chiamando un overload di `ToString` con un parametro *provider* e passando uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7574e-333">You can also format a numeric value for a specific culture by calling a `ToString` overload that has a *provider* parameter and passing it either of the following:</span></span> 

* <span data-ttu-id="7574e-334">Oggetto [CultureInfo](xref:System.Globalization.CultureInfo) che rappresenta le impostazioni cultura, di cui verranno usate le convenzioni di formattazione.</span><span class="sxs-lookup"><span data-stu-id="7574e-334">A [CultureInfo](xref:System.Globalization.CultureInfo) object that represents the culture whose formatting conventions are to be used.</span></span> <span data-ttu-id="7574e-335">Il metodo [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) relativo restituisce il valore della proprietà [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat), che rappresenta l'oggetto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) che offre informazioni di formattazione specifiche delle impostazioni cultura per i valori numerici.</span><span class="sxs-lookup"><span data-stu-id="7574e-335">Its [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) method returns the value of the [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat) property, which is the [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object that provides culture-specific formatting information for numeric values.</span></span>

* <span data-ttu-id="7574e-336">Oggetto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) che definisce le convenzioni di formattazione specifiche delle impostazioni cultura da usare.</span><span class="sxs-lookup"><span data-stu-id="7574e-336">A [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object that defines the culture-specific formatting conventions to be used.</span></span> <span data-ttu-id="7574e-337">Il metodo [GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type)) relativo restituisce un'istanza di se stesso.</span><span class="sxs-lookup"><span data-stu-id="7574e-337">Its [GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type)) method returns an instance of itself.</span></span>

<span data-ttu-id="7574e-338">Nell'esempio seguente vengono usati gli oggetti [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) che rappresentano le impostazioni cultura della lingua inglese di Stati Uniti e di Gran Bretagna, nonché le impostazioni cultura non associate alle lingue francese e russa per formattare un numero a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="7574e-338">The following example uses [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) objects that represent the English (United States) and English (Great Britain) cultures and the French and Russian neutral cultures to format a floating-point number.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {                                                                                                    
      Double value = 1043.62957;
      string[] cultureNames = { "en-US", "en-GB", "ru", "fr" };

      foreach (var name in cultureNames) {
         NumberFormatInfo nfi = CultureInfo.CreateSpecificCulture(name).NumberFormat;
         Console.WriteLine("{0,-6} {1}", name + ":", value.ToString("N3", nfi));
      }   
   }
}
// The example displays the following output:
//       en-US: 1,043.630
//       en-GB: 1,043.630
//       ru:    1 043,630
//       fr:    1 043,630
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim value As Double = 1043.62957
      Dim cultureNames() As String = { "en-US", "en-GB", "ru", "fr" }

      For Each name In cultureNames
         Dim nfi As NumberFormatInfo = CultureInfo.CreateSpecificCulture(name).NumberFormat
         Console.WriteLine("{0,-6} {1}", name + ":", value.ToString("N3", nfi))
      Next   
   End Sub
End Module
' The example displays the following output:
'       en-US: 1,043.630
'       en-GB: 1,043.630
'       ru:    1 043,630
'       fr:    1 043,630
```

### <a name="culture-sensitive-formatting-of-date-and-time-values"></a><span data-ttu-id="7574e-339">Formattazione dipendente dalle impostazioni cultura di valori data e ora</span><span class="sxs-lookup"><span data-stu-id="7574e-339">Culture-sensitive formatting of date and time values</span></span>

<span data-ttu-id="7574e-340">Per impostazione predefinita, la formattazione dei valori data e ora è dipendente dalle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="7574e-340">By default, the formatting of date and time values is culture-sensitive.</span></span> <span data-ttu-id="7574e-341">Se non si specificano impostazioni cultura quando si chiama un metodo di formattazione, vengono usate le convenzioni di formattazione delle impostazioni cultura del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="7574e-341">If you do not specify a culture when you call a formatting method, the formatting conventions of the current thread culture are used.</span></span> <span data-ttu-id="7574e-342">Questa situazione viene illustrata nell'esempio seguente in cui le impostazioni cultura del thread corrente vengono modificate quattro volte e viene chiamato il metodo [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)).</span><span class="sxs-lookup"><span data-stu-id="7574e-342">This is illustrated in the following example, which changes the current thread culture four times and then calls the [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)) method.</span></span> <span data-ttu-id="7574e-343">In ogni caso, la stringa risultante riflette le convenzioni di formattazione delle impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="7574e-343">In each case, the result string reflects the formatting conventions of the current culture.</span></span> <span data-ttu-id="7574e-344">Questo avviene perché i metodi [DateTime.ToString()](xref:System.DateTime.ToString), [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)), [DateTimeOffset.ToString()](xref:System.DateTimeOffset.ToString(System.String)) e [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String)) eseguono il wrapping delle chiamate ai metodi [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) e [DateTimeOffset.ToString(String, IFormatProvider)](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)).</span><span class="sxs-lookup"><span data-stu-id="7574e-344">This is because the [DateTime.ToString()](xref:System.DateTime.ToString), [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)), [DateTimeOffset.ToString()](xref:System.DateTimeOffset.ToString(System.String)), and [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String)) methods wrap calls to the [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) and [DateTimeOffset.ToString(String, IFormatProvider)](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) methods.</span></span>

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] cultureNames = { "en-US", "fr-FR", "es-MX", "de-DE" };
      DateTime dateToFormat = new DateTime(2012, 5, 28, 11, 30, 0);

      foreach (var cultureName in cultureNames) {
         // Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName);
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name);
         Console.WriteLine(dateToFormat.ToString("F"));
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//       The current culture is en-US
//       Monday, May 28, 2012 11:30:00 AM
//       
//       The current culture is fr-FR
//       lundi 28 mai 2012 11:30:00
//       
//       The current culture is es-MX
//       lunes, 28 de mayo de 2012 11:30:00 a.m.
//       
//       The current culture is de-DE
//       Montag, 28. Mai 2012 11:30:00
```

```vb
Imports System.Globalization
Imports System.Threading 

Module Example
   Public Sub Main()
      Dim cultureNames() As String = { "en-US", "fr-FR", "es-MX", "de-DE" }
      Dim dateToFormat As Date = #5/28/2012 11:30AM#

      For Each cultureName In cultureNames
         ' Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName)
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name)
         Console.WriteLine(dateToFormat.ToString("F"))
         Console.WriteLine()
      Next                  
   End Sub
End Module
' The example displays the following output:
'       The current culture is en-US
'       Monday, May 28, 2012 11:30:00 AM
'       
'       The current culture is fr-FR
'       lundi 28 mai 2012 11:30:00
'       
'       The current culture is es-MX
'       lunes, 28 de mayo de 2012 11:30:00 a.m.
'       
'       The current culture is de-DE
'       Montag, 28. Mai 2012 11:30:00
```

<span data-ttu-id="7574e-345">È anche possibile formattare un valore data e ora per impostazioni cultura specifiche chiamando un overload [DateTime.ToString](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) o [DateTimeOffset.ToString](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) contenente un parametro provider e passandolo agli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7574e-345">You can also format a date and time value for a specific culture by calling a [DateTime.ToString](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) or [DateTimeOffset.ToString](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) overload that has a provider parameter and passing it either of the following:</span></span> 

* <span data-ttu-id="7574e-346">Oggetto [CultureInfo](xref:System.Globalization.CultureInfo) che rappresenta le impostazioni cultura, di cui verranno usate le convenzioni di formattazione.</span><span class="sxs-lookup"><span data-stu-id="7574e-346">A [CultureInfo](xref:System.Globalization.CultureInfo) object that represents the culture whose formatting conventions are to be used.</span></span> <span data-ttu-id="7574e-347">Il metodo [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) relativo restituisce il valore della proprietà [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat), che rappresenta l'oggetto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) che offre informazioni di formattazione specifiche delle impostazioni cultura per i valori numerici.</span><span class="sxs-lookup"><span data-stu-id="7574e-347">Its [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) method returns the value of the [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat) property, which is the [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object that provides culture-specific formatting information for numeric values.</span></span>

* <span data-ttu-id="7574e-348">Oggetto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) che definisce le convenzioni di formattazione specifiche delle impostazioni cultura da usare.</span><span class="sxs-lookup"><span data-stu-id="7574e-348">A [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object that defines the culture-specific formatting conventions to be used.</span></span> <span data-ttu-id="7574e-349">Il metodo [GetFormat](xref:System.Globalization.DateTimeFormatInfo.GetFormat(System.Type)) relativo restituisce un'istanza di se stesso.</span><span class="sxs-lookup"><span data-stu-id="7574e-349">Its [GetFormat](xref:System.Globalization.DateTimeFormatInfo.GetFormat(System.Type)) method returns an instance of itself.</span></span>

<span data-ttu-id="7574e-350">Nell'esempio seguente vengono usati gli oggetti [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) che rappresentano le impostazioni cultura della lingua inglese di Stati Uniti e Gran Bretagna e le impostazioni cultura non associate alle lingue francese e russa per formattare una data.</span><span class="sxs-lookup"><span data-stu-id="7574e-350">The following example uses [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) objects that represent the English (United States) and English (Great Britain) cultures and the French and Russian neutral cultures to format a date.</span></span> 

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {                                                                                                    
      DateTime dat1 = new DateTime(2012, 5, 28, 11, 30, 0);
      string[] cultureNames = { "en-US", "en-GB", "ru", "fr" };

      foreach (var name in cultureNames) {
         DateTimeFormatInfo dtfi = CultureInfo.CreateSpecificCulture(name).DateTimeFormat;
         Console.WriteLine("{0}: {1}", name, dat1.ToString(dtfi));
      }   
   }
}
// The example displays the following output:
//       en-US: 5/28/2012 11:30:00 AM
//       en-GB: 28/05/2012 11:30:00
//       ru: 28.05.2012 11:30:00
//       fr: 28/05/2012 11:30:00
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim dat1 As Date = #5/28/2012 11:30AM#
      Dim cultureNames() As String = { "en-US", "en-GB", "ru", "fr" }

      For Each name In cultureNames
         Dim dtfi As DateTimeFormatInfo = CultureInfo.CreateSpecificCulture(name).DateTimeFormat
         Console.WriteLine("{0}: {1}", name, dat1.ToString(dtfi))
      Next   
   End Sub
End Module
' The example displays the following output:
'       en-US: 5/28/2012 11:30:00 AM
'       en-GB: 28/05/2012 11:30:00
'       ru: 28.05.2012 11:30:00
'       fr: 28/05/2012 11:30:00
```

## <a name="the-iformattable-interface"></a><span data-ttu-id="7574e-351">Interfaccia IFormattable</span><span class="sxs-lookup"><span data-stu-id="7574e-351">The IFormattable interface</span></span>

<span data-ttu-id="7574e-352">In genere, i tipi che eseguono l'overload del metodo `ToString` con una stringa di formato e un parametro [IFormatProvider](xref:System.IFormatProvider) implementano anche l'interfaccia [IFormattable](xref:System.IFormattable).</span><span class="sxs-lookup"><span data-stu-id="7574e-352">Typically, types that overload the `ToString` method with a format string and an [IFormatProvider](xref:System.IFormatProvider) parameter also implement the [IFormattable](xref:System.IFormattable) interface.</span></span> <span data-ttu-id="7574e-353">Questa interfaccia dispone di un singolo membro, [IFormattable.ToString(String, IFormatProvider)](xref:System.IFormattable.ToString(System.String,System.IFormatProvider)), che include sia una stringa di formato che un provider di formato come parametri.</span><span class="sxs-lookup"><span data-stu-id="7574e-353">This interface has a single member, [IFormattable.ToString(String, IFormatProvider)](xref:System.IFormattable.ToString(System.String,System.IFormatProvider)), that includes both a format string and a format provider as parameters.</span></span>

<span data-ttu-id="7574e-354">L'implementazione dell'interfaccia [IFormattable](xref:System.IFormattable) per la classe definita dall'applicazione offre due vantaggi:</span><span class="sxs-lookup"><span data-stu-id="7574e-354">Implementing the [IFormattable](xref:System.IFormattable) interface for your application-defined class offers two advantages:</span></span> 

* <span data-ttu-id="7574e-355">Supporto per la conversione di stringhe da parte della classe [Convert](xref:System.Convert).</span><span class="sxs-lookup"><span data-stu-id="7574e-355">Support for string conversion by the [Convert](xref:System.Convert) class.</span></span> <span data-ttu-id="7574e-356">Le chiamate ai metodi [Convert.ToString(Object)](xref:System.Convert.ToString(System.Object)) e [Convert.ToString(Object, IFormatProvider)](xref:System.Convert.ToString(System.Object,System.IFormatProvider)) chiamano automaticamente l'implementazione di [IFormattable](xref:System.IFormattable).</span><span class="sxs-lookup"><span data-stu-id="7574e-356">Calls to the [Convert.ToString(Object)](xref:System.Convert.ToString(System.Object)) and [Convert.ToString(Object, IFormatProvider)](xref:System.Convert.ToString(System.Object,System.IFormatProvider)) methods call your [IFormattable](xref:System.IFormattable) implementation automatically.</span></span>

* <span data-ttu-id="7574e-357">Supporto per la formattazione composita.</span><span class="sxs-lookup"><span data-stu-id="7574e-357">Support for composite formatting.</span></span> <span data-ttu-id="7574e-358">Se viene usato un elemento di formato che include una stringa di formato per formattare il tipo personalizzato, tramite Common Language Runtime viene chiamata automaticamente l'implementazione di [IFormattable](xref:System.IFormattable), che viene passata alla stringa di formato.</span><span class="sxs-lookup"><span data-stu-id="7574e-358">If a format item that includes a format string is used to format your custom type, the Common Language Runtime automatically calls your [IFormattable](xref:System.IFormattable) implementation and passes it the format string.</span></span> <span data-ttu-id="7574e-359">Per altre informazioni sulla formattazione composita con metodi come `String.Format` o `Console.WriteLine`, vedere la sezione [Formattazione composita](#composite-formatting).</span><span class="sxs-lookup"><span data-stu-id="7574e-359">For more information about composite formatting with methods such as `String.Format` or `Console.WriteLine`, see the [Composite formatting](#composite-formatting) section.</span></span>

<span data-ttu-id="7574e-360">Nell'esempio seguente viene definita una classe `Temperature` che implementa l'interfaccia [IFormattable](xref:System.IFormattable).</span><span class="sxs-lookup"><span data-stu-id="7574e-360">The following example defines a `Temperature` class that implements the [IFormattable](xref:System.IFormattable) interface.</span></span> <span data-ttu-id="7574e-361">Sono supportati gli identificatori di formato "C" e "G" per visualizzare la temperatura in Celsius, l'identificatore di formato "F" per visualizzare la temperatura in Fahrenheit e l'identificatore di formato "K" per visualizzare la temperatura in Kelvin.</span><span class="sxs-lookup"><span data-stu-id="7574e-361">It supports the "C" or "G" format specifiers to display the temperature in Celsius, the "F" format specifier to display the temperature in Fahrenheit, and the "K" format specifier to display the temperature in Kelvin.</span></span>

```csharp
using System;
using System.Globalization;

public class Temperature : IFormattable
{
   private decimal m_Temp;

   public Temperature(decimal temperature)
   {
      this.m_Temp = temperature;
   }

   public decimal Celsius
   {
      get { return this.m_Temp; }
   }

   public decimal Kelvin
   {
      get { return this.m_Temp + 273.15m; }   
   }

   public decimal Fahrenheit
   {
      get { return Math.Round((decimal) this.m_Temp * 9 / 5 + 32, 2); }
   }

   public override string ToString()
   {
      return this.ToString("G", null);
   }

   public string ToString(string format)
   {
      return this.ToString(format, null);
   }

   public string ToString(string format, IFormatProvider provider)  
   {
      // Handle null or empty arguments.
      if (String.IsNullOrEmpty(format)) format = "G";
      // Remove any white space and convert to uppercase.
      format = format.Trim().ToUpperInvariant();

      if (provider == null) provider = NumberFormatInfo.CurrentInfo;

      switch (format)
      {
         // Convert temperature to Fahrenheit and return string.
         case "F":
            return this.Fahrenheit.ToString("N2", provider) + "°F";
         // Convert temperature to Kelvin and return string.
         case "K":
            return this.Kelvin.ToString("N2", provider) + "K";
         // Return temperature in Celsius.
         case "C":
         case "G":
            return this.Celsius.ToString("N2", provider) + "°C";
         default:
            throw new FormatException(String.Format("The '{0}' format string is not supported.", format));
      }      
   }
}
```

```vb
Imports System.Globalization

Public Class Temperature : Implements IFormattable
   Private m_Temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.m_Temp = temperature
   End Sub

   Public ReadOnly Property Celsius() As Decimal
      Get
         Return Me.m_Temp
      End Get   
   End Property

   Public ReadOnly Property Kelvin() As Decimal
      Get
         Return Me.m_Temp + 273.15d   
      End Get
   End Property

   Public ReadOnly Property Fahrenheit() As Decimal
      Get
         Return Math.Round(CDec(Me.m_Temp * 9 / 5 + 32), 2)
      End Get      
   End Property

   Public Overrides Function ToString() As String
      Return Me.ToString("G", Nothing)
   End Function

   Public Overloads Function ToString(format As String) As String
      Return Me.ToString(format, Nothing)
   End Function

   Public Overloads Function ToString(format As String, provider As IFormatProvider) As String _  
      Implements IFormattable.ToString

      ' Handle null or empty arguments.
      If String.IsNullOrEmpty(format) Then format = "G"
      ' Remove any white space and convert to uppercase.
      format = format.Trim().ToUpperInvariant()

      If provider Is Nothing Then provider = NumberFormatInfo.CurrentInfo

      Select Case format
         ' Convert temperature to Fahrenheit and return string.
         Case "F"
            Return Me.Fahrenheit.ToString("N2", provider) & "°F"
         ' Convert temperature to Kelvin and return string.
         Case "K"
            Return Me.Kelvin.ToString("N2", provider) & "K"
         ' Return temperature in Celsius.
         Case "C", "G"
            Return Me.Celsius.ToString("N2", provider) & "°C"
         Case Else
            Throw New FormatException(String.Format("The '{0}' format string is not supported.", format))
      End Select      
   End Function
End Class
```

<span data-ttu-id="7574e-362">Nell'esempio seguente viene creata un'istanza di un oggetto `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="7574e-362">The following example instantiates a `Temperature` object.</span></span> <span data-ttu-id="7574e-363">Viene quindi chiamato il metodo [ToString](xref:System.Convert.ToString(System.Object,System.IFormatProvider)) e vengono usate diverse stringhe di formato composite per ottenere diverse rappresentazioni di stringa di un oggetto `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="7574e-363">It then calls the [ToString](xref:System.Convert.ToString(System.Object,System.IFormatProvider)) method and uses several composite format strings to obtain different string representations of a `Temperature` object.</span></span> <span data-ttu-id="7574e-364">Ognuna di queste chiamate al metodo chiama, a sua volta, l'implementazione di [IFormattable](xref:System.IFormattable) della classe `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="7574e-364">Each of these method calls, in turn, calls the [IFormattable](xref:System.IFormattable) implementation of the `Temperature` class.</span></span>

```csharp
public class Example
{
   public static void Main()
   {
      Temperature temp1 = new Temperature(22m);
      Console.WriteLine(Convert.ToString(temp1, new CultureInfo("ja-JP")));
      Console.WriteLine("Temperature: {0:K}", temp1);
      Console.WriteLine("Temperature: {0:F}", temp1);
      Console.WriteLine(String.Format(new CultureInfo("fr-FR"), "Temperature: {0:F}", temp1));
   }
}
// The example displays the following output:
//       22.00°C
//       Temperature: 295.15°K
//       Temperature: 71.60°F
//       Temperature: 71,60°F
```

```vb
Public Module Example
   Public Sub Main()
      Dim temp1 As New Temperature(22d)
      Console.WriteLine(Convert.ToString(temp1, New CultureInfo("ja-JP")))
      Console.WriteLine("Temperature: {0:K}", temp1)
      Console.WriteLine("Temperature: {0:F}", temp1)
      Console.WriteLine(String.Format(New CultureInfo("fr-FR"), "Temperature: {0:F}", temp1)) 
   End Sub
End Module
' The example displays the following output:
'       22.00°C
'       Temperature: 295.15°K
'       Temperature: 71.60°F
'       Temperature: 71,60°F
```

## <a name="composite-formatting"></a><span data-ttu-id="7574e-365">Formattazione composita</span><span class="sxs-lookup"><span data-stu-id="7574e-365">Composite formatting</span></span>

<span data-ttu-id="7574e-366">Alcuni metodi, ad esempio `String.Format` e `StringBuilder.AppendFormat`, supportano la formattazione composita.</span><span class="sxs-lookup"><span data-stu-id="7574e-366">Some methods, such as `String.Format` and `StringBuilder.AppendFormat`, support composite formatting.</span></span> <span data-ttu-id="7574e-367">Una stringa di formato composita è un tipo di modello che restituisce una singola stringa che incorpora la rappresentazione di stringa di zero, uno o più oggetti.</span><span class="sxs-lookup"><span data-stu-id="7574e-367">A composite format string is a kind of template that returns a single string that incorporates the string representation of zero, one, or more objects.</span></span> <span data-ttu-id="7574e-368">Ogni oggetto è rappresentato nella stringa di formato composita da un elemento di formato indicizzato.</span><span class="sxs-lookup"><span data-stu-id="7574e-368">Each object is represented in the composite format string by an indexed format item.</span></span> <span data-ttu-id="7574e-369">L'indice dell'elemento di formato corrisponde alla posizione dell'oggetto che esso rappresenta nell'elenco di parametri del metodo.</span><span class="sxs-lookup"><span data-stu-id="7574e-369">The index of the format item corresponds to the position of the object that it represents in the method's parameter list.</span></span> <span data-ttu-id="7574e-370">Gli indici sono a base zero.</span><span class="sxs-lookup"><span data-stu-id="7574e-370">Indexes are zero-based.</span></span> <span data-ttu-id="7574e-371">Nella chiamata seguente al metodo `String.Format`, ad esempio, il primo elemento di formato, `{0:D}`, viene sostituito dalla rappresentazione di stringa `thatDate`, il secondo elemento di formato, `{1}`, viene sostituito dalla rappresentazione di stringa `item1` e il terzo elemento di formato, `{2:C2}`, viene sostituito dalla rappresentazione di stringa `item1.Value`.</span><span class="sxs-lookup"><span data-stu-id="7574e-371">For example, in the following call to the `String.Format` method, the first format item, `{0:D}`, is replaced by the string representation of `thatDate`; the second format item, `{1}`, is replaced by the string representation of `item1`; and the third format item, `{2:C2}`, is replaced by the string representation of `item1.Value`.</span></span>

```csharp
result = String.Format("On {0:d}, the inventory of {1} was worth {2:C2}.", 
                       thatDate, item1, item1.Value);
Console.WriteLine(result);                            
// The example displays output like the following if run on a system
// whose current culture is en-US:
//       On 5/1/2009, the inventory of WidgetA was worth $107.44.
```

```vb
result = String.Format("On {0:d}, the inventory of {1} was worth {2:C2}.", _
                       thatDate, item1, item1.Value)
Console.WriteLine(result)                            
' The example displays output like the following if run on a system
' whose current culture is en-US:
'       On 5/1/2009, the inventory of WidgetA was worth $107.44.
```

<span data-ttu-id="7574e-372">Oltre a sostituire un elemento di formato con la rappresentazione di stringa dell'oggetto corrispondente, gli elementi di formato consentono anche di controllare gli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7574e-372">In addition to replacing a format item with the string representation of its corresponding object, format items also let you control the following:</span></span> 

* <span data-ttu-id="7574e-373">Il modo specifico in cui un oggetto è rappresentato come stringa, se l'oggetto implementa l'interfaccia [IFormattable](xref:System.IFormattable) e supporta le stringhe di formato.</span><span class="sxs-lookup"><span data-stu-id="7574e-373">The specific way in which an object is represented as a string, if the object implements the [IFormattable](xref:System.IFormattable) interface and supports format strings.</span></span> <span data-ttu-id="7574e-374">A tale scopo, dopo l'indice dell'elemento di formato è necessario aggiungere un simbolo : (due punti) seguito da una stringa di formato valida.</span><span class="sxs-lookup"><span data-stu-id="7574e-374">You do this by following the format item's index with a : (colon) followed by a valid format string.</span></span> <span data-ttu-id="7574e-375">Nell'esempio precedente viene eseguita questa operazione formattando un valore di data con la stringa di formato "d" (modello di data breve) (ad esempio, `{0:d}`) e formattando un valore numerico con la stringa di formato "C2" (ad esempio, `{2:C2}`) per rappresentare il numero come valore di valuta con due cifre decimali.</span><span class="sxs-lookup"><span data-stu-id="7574e-375">The previous example did this by formatting a date value with the "d" (short date pattern) format string (for example, `{0:d}`) and by formatting a numeric value with the "C2" format string (for example, `{2:C2}` to represent the number as a currency value with two fractional decimal digits).</span></span> 

* <span data-ttu-id="7574e-376">La larghezza del campo che contiene la rappresentazione di stringa dell'oggetto e l'allineamento della rappresentazione di stringa in tale campo.</span><span class="sxs-lookup"><span data-stu-id="7574e-376">The width of the field that contains the object's string representation, and the alignment of the string representation in that field.</span></span> <span data-ttu-id="7574e-377">A tale scopo, dopo l'indice dell'elemento di formato è necessario aggiungere un simbolo , (virgola) seguito dalla larghezza del campo.</span><span class="sxs-lookup"><span data-stu-id="7574e-377">You do this by following the format item's index with a , (comma) followed the field width.</span></span> <span data-ttu-id="7574e-378">La stringa viene allineata a destra nel campo se la larghezza del campo è un valore positivo e viene allineata a sinistra se la larghezza del campo è un valore negativo.</span><span class="sxs-lookup"><span data-stu-id="7574e-378">The string is right-aligned in the field if the field width is a positive value, and it is left-aligned if the field width is a negative value.</span></span> <span data-ttu-id="7574e-379">L'esempio seguente consente di allineare a sinistra i valori di data in un campo di 20 caratteri e di allineare a destra i valori decimali con una cifra frazionaria in un campo di 11 caratteri.</span><span class="sxs-lookup"><span data-stu-id="7574e-379">The following example left-aligns date values in a 20-character field, and it right-aligns decimal values with one fractional digit in an 11-character field.</span></span> 

```csharp
DateTime startDate = new DateTime(2015, 8, 28, 6, 0, 0);
decimal[] temps = { 73.452m, 68.98m, 72.6m, 69.24563m,
                   74.1m, 72.156m, 72.228m };
Console.WriteLine("{0,-20} {1,11}\n", "Date", "Temperature");
for (int ctr = 0; ctr < temps.Length; ctr++)
   Console.WriteLine("{0,-20:g} {1,11:N1}", startDate.AddDays(ctr), temps[ctr]);

// The example displays the following output:
//       Date                 Temperature
//
//       8/28/2015 6:00 AM           73.5
//       8/29/2015 6:00 AM           69.0
//       8/30/2015 6:00 AM           72.6
//       8/31/2015 6:00 AM           69.2
//       9/1/2015 6:00 AM            74.1
//       9/2/2015 6:00 AM            72.2
//       9/3/2015 6:00 AM            72.2
```

```vb
Dim startDate As New Date(2015, 8, 28, 6, 0, 0)
Dim temps() As Decimal = { 73.452, 68.98, 72.6, 69.24563,
                           74.1, 72.156, 72.228 }
Console.WriteLine("{0,-20} {1,11}", "Date", "Temperature")
Console.WriteLine()
For ctr As Integer = 0 To temps.Length - 1
   Console.WriteLine("{0,-20:g} {1,11:N1}", startDate.AddDays(ctr), temps(ctr))
Next
' The example displays the following output:
'       Date                 Temperature
'
'       8/28/2015 6:00 AM           73.5
'       8/29/2015 6:00 AM           69.0
'       8/30/2015 6:00 AM           72.6
'       8/31/2015 6:00 AM           69.2
'       9/1/2015 6:00 AM            74.1
'       9/2/2015 6:00 AM            72.2
'       9/3/2015 6:00 AM            72.2
```

<span data-ttu-id="7574e-380">Si noti che, se il componente stringa di allineamento e il componente stringa di formato sono entrambi presenti, il primo precede il secondo, ad esempio `{0,-20:g}`.</span><span class="sxs-lookup"><span data-stu-id="7574e-380">Note that, if both the alignment string component and the format string component are present, the former precedes the latter (for example, `{0,-20:g}`.</span></span> 

<span data-ttu-id="7574e-381">Per altre informazioni sulla formattazione composita, vedere [Formattazione composita](composite-format.md).</span><span class="sxs-lookup"><span data-stu-id="7574e-381">For more information about composite formatting, see [Composite formatting](composite-format.md).</span></span>

## <a name="custom-formatting-with-icustomformatter"></a><span data-ttu-id="7574e-382">Formattazione personalizzata con ICustomFormatter</span><span class="sxs-lookup"><span data-stu-id="7574e-382">Custom formatting with ICustomFormatter</span></span>

<span data-ttu-id="7574e-383">Due metodi di formattazione composita, [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object[])) e [StringBuilder.AppendFormat(IFormatProvider, String, Object[])](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)), includono un parametro del provider di formato che supporta la formattazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="7574e-383">Two composite formatting methods, [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object[])) and [StringBuilder.AppendFormat(IFormatProvider, String, Object[])](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)), include a format provider parameter that supports custom formatting.</span></span> <span data-ttu-id="7574e-384">Quando viene chiamato uno di questi metodi di formattazione, viene passato un oggetto [Type](xref:System.Type) che rappresenta un'interfaccia [ICustomFormatter](xref:System.ICustomFormatter) al metodo `GetFormat` del provider di formato.</span><span class="sxs-lookup"><span data-stu-id="7574e-384">When either of these formatting methods is called, it passes a [Type](xref:System.Type) object that represents an [ICustomFormatter](xref:System.ICustomFormatter) interface to the format provider’s `GetFormat` method.</span></span> <span data-ttu-id="7574e-385">Il metodo `GetFormat` è quindi responsabile della restituzione dell'implementazione di [ICustomFormatter](xref:System.ICustomFormatter) che fornisce formattazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="7574e-385">The `GetFormat` method is then responsible for returning the [ICustomFormatter](xref:System.ICustomFormatter) implementation that provides custom formatting.</span></span>

<span data-ttu-id="7574e-386">L'interfaccia [ICustomFormatter](xref:System.ICustomFormatter) ha un singolo metodo, [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)), chiamato automaticamente da un metodo di formattazione composita una volta per ogni elemento di formato in una stringa di formato composita.</span><span class="sxs-lookup"><span data-stu-id="7574e-386">The [ICustomFormatter](xref:System.ICustomFormatter) interface has a single method, [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)), that is called automatically by a composite formatting method, once for each format item in a composite format string.</span></span> <span data-ttu-id="7574e-387">Il metodo [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) ha tre parametri: una stringa di formato, che rappresenta l'argomento *formatString* in un elemento di formato, un oggetto da formattare e un oggetto [IFormatProvider](xref:System.IFormatProvider) che fornisce i servizi di formattazione.</span><span class="sxs-lookup"><span data-stu-id="7574e-387">The [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) method has three parameters: a format string, which represents the *formatString* argument in a format item, an object to format, and an [IFormatProvider](xref:System.IFormatProvider) object that provides formatting services.</span></span> <span data-ttu-id="7574e-388">In genere, la classe che implementa [ICustomFormatter](xref:System.ICustomFormatter) implementa anche [IFormatProvider](xref:System.IFormatProvider), pertanto quest'ultimo parametro è un riferimento alla classe di formattazione personalizzata stessa.</span><span class="sxs-lookup"><span data-stu-id="7574e-388">Typically, the class that implements [ICustomFormatter](xref:System.ICustomFormatter) also implements [IFormatProvider](xref:System.IFormatProvider), so this last parameter is a reference to the custom formatting class itself.</span></span> <span data-ttu-id="7574e-389">Questo metodo restituisce una rappresentazione di stringa formattata personalizzata dell'oggetto da formattare.</span><span class="sxs-lookup"><span data-stu-id="7574e-389">The method returns a custom formatted string representation of the object to be formatted.</span></span> <span data-ttu-id="7574e-390">Se il metodo non è in grado di formattare l'oggetto, deve restituire un riferimento Null.</span><span class="sxs-lookup"><span data-stu-id="7574e-390">If the method cannot format the object, it should return a null reference.</span></span>

<span data-ttu-id="7574e-391">Nell'esempio seguente viene fornita un'implementazione di [ICustomFormatter](xref:System.ICustomFormatter) denominata `ByteByByteFormatter` che consente di visualizzare i valori interi come sequenza di valori esadecimali a due cifre seguiti da uno spazio.</span><span class="sxs-lookup"><span data-stu-id="7574e-391">The following example provides an [ICustomFormatter](xref:System.ICustomFormatter) implementation named `ByteByByteFormatter` that displays integer values as a sequence of two-digit hexadecimal values followed by a space.</span></span>

```csharp
public class ByteByByteFormatter : IFormatProvider, ICustomFormatter
{
   public object GetFormat(Type formatType)
   { 
      if (formatType == typeof(ICustomFormatter))
         return this;
      else
         return null;
   }

   public string Format(string format, object arg, 
                          IFormatProvider formatProvider)
   {   
      if (! formatProvider.Equals(this)) return null;

      // Handle only hexadecimal format string.
      if (! format.StartsWith("X")) return null;

      byte[] bytes;
      string output = null;

      // Handle only integral types.
      if (arg is Byte) 
         bytes = BitConverter.GetBytes((Byte) arg);
      else if (arg is Int16)
         bytes = BitConverter.GetBytes((Int16) arg);
      else if (arg is Int32)
         bytes = BitConverter.GetBytes((Int32) arg);
      else if (arg is Int64)   
         bytes = BitConverter.GetBytes((Int64) arg);
      else if (arg is SByte)
         bytes = BitConverter.GetBytes((SByte) arg);
      else if (arg is UInt16)
         bytes = BitConverter.GetBytes((UInt16) arg);
      else if (arg is UInt32)
         bytes = BitConverter.GetBytes((UInt32) arg);
      else if (arg is UInt64)
         bytes = BitConverter.GetBytes((UInt64) arg);
      else
         return null;

      for (int ctr = bytes.Length - 1; ctr >= 0; ctr--)
         output += String.Format("{0:X2} ", bytes[ctr]);   

      return output.Trim();
   }
}
```

```vb
Public Class ByteByByteFormatter : Implements IFormatProvider, ICustomFormatter
   Public Function GetFormat(formatType As Type) As Object _
                   Implements IFormatProvider.GetFormat
      If formatType Is GetType(ICustomFormatter) Then
         Return Me
      Else
         Return Nothing
      End If
   End Function

   Public Function Format(fmt As String, arg As Object, 
                          formatProvider As IFormatProvider) As String _
                          Implements ICustomFormatter.Format

      If Not formatProvider.Equals(Me) Then Return Nothing

      ' Handle only hexadecimal format string.
      If Not fmt.StartsWith("X") Then 
            Return Nothing
      End If

      ' Handle only integral types.
      If Not typeof arg Is Byte AndAlso
         Not typeof arg Is Int16 AndAlso
         Not typeof arg Is Int32 AndAlso
         Not typeof arg Is Int64 AndAlso
         Not typeof arg Is SByte AndAlso
         Not typeof arg Is UInt16 AndAlso
         Not typeof arg Is UInt32 AndAlso
         Not typeof arg Is UInt64 Then _
            Return Nothing

      Dim bytes() As Byte = BitConverter.GetBytes(arg)
      Dim output As String = Nothing

      For ctr As Integer = bytes.Length - 1 To 0 Step -1
         output += String.Format("{0:X2} ", bytes(ctr))   
      Next

      Return output.Trim()
   End Function
End Class
```

<span data-ttu-id="7574e-392">Nell'esempio seguente viene usata la classe `ByteByByteFormatter` per formattare valori interi.</span><span class="sxs-lookup"><span data-stu-id="7574e-392">The following example uses the `ByteByByteFormatter` class to format integer values.</span></span> <span data-ttu-id="7574e-393">Si noti che il metodo [ICustomFormatter.Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) viene chiamato più di una volta nella seconda chiamata al metodo [String.Format(IFormatProvider, String, Object[])](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) e che il provider [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) predefinito viene usato nella terza chiamata al metodo, in quanto il metodo `.ByteByByteFormatter.Format` non riconosce la stringa di formato "N0" e restituisce un riferimento Null.</span><span class="sxs-lookup"><span data-stu-id="7574e-393">Note that the [ICustomFormatter.Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) method is called more than once in the second [String.Format(IFormatProvider, String, Object[])](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) method call, and that the default [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) provider is used in the third method call because the `.ByteByByteFormatter.Format` method does not recognize the "N0" format string and returns a null reference.</span></span>

```csharp
public class Example
{
   public static void Main()
   {
      long value = 3210662321; 
      byte value1 = 214;
      byte value2 = 19;

      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0:X}", value));
      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0:X} And {1:X} = {2:X} ({2:000})", 
                                      value1, value2, value1 & value2));                                
      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0,10:N0}", value));
   }
}
// The example displays the following output:
//       00 00 00 00 BF 5E D1 B1
//       00 D6 And 00 13 = 00 12 (018)
//       3,210,662,321
```

```vb
Public Module Example
   Public Sub Main()
      Dim value As Long = 3210662321 
      Dim value1 As Byte = 214
      Dim value2 As Byte = 19

      Console.WriteLine((String.Format(New ByteByByteFormatter(), "{0:X}", value)))
      Console.WriteLine((String.Format(New ByteByByteFormatter(), "{0:X} And {1:X} = {2:X} ({2:000})", 
                                      value1, value2, value1 And value2)))                                
      Console.WriteLine(String.Format(New ByteByByteFormatter(), "{0,10:N0}", value))
   End Sub
End Module
' The example displays the following output:
'       00 00 00 00 BF 5E D1 B1
'       00 D6 And 00 13 = 00 12 (018)
'       3,210,662,321
```

## <a name="related-topics"></a><span data-ttu-id="7574e-394">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7574e-394">Related topics</span></span>

<span data-ttu-id="7574e-395">Titolo</span><span class="sxs-lookup"><span data-stu-id="7574e-395">Title</span></span> | <span data-ttu-id="7574e-396">Definizione</span><span class="sxs-lookup"><span data-stu-id="7574e-396">Definition</span></span>
----- | ----------
[<span data-ttu-id="7574e-397">Stringhe di formato numerico standard</span><span class="sxs-lookup"><span data-stu-id="7574e-397">Standard numeric format strings</span></span>](standard-numeric.md) | <span data-ttu-id="7574e-398">Vengono descritte le stringhe di formato standard che consentono di creare rappresentazioni di stringa usate comunemente di valori numerici.</span><span class="sxs-lookup"><span data-stu-id="7574e-398">Describes standard format strings that create commonly used string representations of numeric values.</span></span> 
[<span data-ttu-id="7574e-399">Stringhe di formato numerico personalizzato</span><span class="sxs-lookup"><span data-stu-id="7574e-399">Custom numeric format strings</span></span>](custom-numeric.md) | <span data-ttu-id="7574e-400">Vengono descritte le stringhe di formato personalizzate che consentono di creare formati specifici dell'applicazione per valori numerici.</span><span class="sxs-lookup"><span data-stu-id="7574e-400">Describes custom format strings that create application-specific formats for numeric values.</span></span>
[<span data-ttu-id="7574e-401">Stringhe di formato di data e ora standard</span><span class="sxs-lookup"><span data-stu-id="7574e-401">Standard date and time format strings</span></span>](standard-datetime.md) |  <span data-ttu-id="7574e-402">Vengono descritte le stringhe di formato standard che consentono di creare rappresentazioni di stringa usate comunemente di valori [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="7574e-402">Describes standard format strings that create commonly used string representations of [DateTime](xref:System.DateTime) values.</span></span>
[<span data-ttu-id="7574e-403">Stringhe di formato di data e ora personalizzato</span><span class="sxs-lookup"><span data-stu-id="7574e-403">Custom date and time format strings</span></span>](custom-datetime.md) | <span data-ttu-id="7574e-404">Vengono descritte le stringhe di formato personalizzate che consentono di creare formati specifici dell'applicazione per valori [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="7574e-404">Describes custom format strings that create application-specific formats for [DateTime](xref:System.DateTime) values.</span></span>
[<span data-ttu-id="7574e-405">Stringhe di formato TimeSpan standard</span><span class="sxs-lookup"><span data-stu-id="7574e-405">Standard TimeSpan format strings</span></span>](standard-timespan.md) | <span data-ttu-id="7574e-406">Vengono descritte le stringhe di formato standard che consentono di creare rappresentazioni di stringa usate comunemente di intervalli di tempo.</span><span class="sxs-lookup"><span data-stu-id="7574e-406">Describes standard format strings that create commonly used string representations of time intervals.</span></span>
[<span data-ttu-id="7574e-407">Stringhe di formato TimeSpan personalizzate</span><span class="sxs-lookup"><span data-stu-id="7574e-407">Custom TimeSpan format strings</span></span>](custom-timespan.md) | <span data-ttu-id="7574e-408">Vengono descritte le stringhe di formato personalizzate che consentono di creare formati specifici dell'applicazione per intervalli di tempo.</span><span class="sxs-lookup"><span data-stu-id="7574e-408">Describes custom format strings that create application-specific formats for time intervals.</span></span>
[<span data-ttu-id="7574e-409">Stringhe di formato di enumerazione</span><span class="sxs-lookup"><span data-stu-id="7574e-409">Enumeration format strings</span></span>](enumeration-format.md) | <span data-ttu-id="7574e-410">Vengono descritte le stringhe di formato standard che consentono di creare rappresentazioni di stringa di valori di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="7574e-410">Describes standard format strings that are used to create string representations of enumeration values.</span></span>
[<span data-ttu-id="7574e-411">Formattazione composita</span><span class="sxs-lookup"><span data-stu-id="7574e-411">Composite formatting</span></span>](composite-format.md) | <span data-ttu-id="7574e-412">Viene descritto come incorporare uno o più valori formattati in una stringa,</span><span class="sxs-lookup"><span data-stu-id="7574e-412">Describes how to embed one or more formatted values in a string.</span></span> <span data-ttu-id="7574e-413">che successivamente può essere visualizzata nella console oppure scritta in un flusso.</span><span class="sxs-lookup"><span data-stu-id="7574e-413">The string can subsequently be displayed on the console or written to a stream.</span></span>
[<span data-ttu-id="7574e-414">Esecuzione di operazioni di formattazione</span><span class="sxs-lookup"><span data-stu-id="7574e-414">Performing formatting operations</span></span>](performing-formatting-operations.md) | <span data-ttu-id="7574e-415">Sono elencati gli argomenti contenenti istruzioni dettagliate per l'esecuzione di operazioni di formattazione specifiche.</span><span class="sxs-lookup"><span data-stu-id="7574e-415">Lists topics that provide step-by-step instructions for performing specific formatting operations.</span></span>
[<span data-ttu-id="7574e-416">Analisi di stringhe</span><span class="sxs-lookup"><span data-stu-id="7574e-416">Parsing strings</span></span>](parsing-strings.md) | <span data-ttu-id="7574e-417">Viene descritta l'inizializzazione di oggetti sui valori descritti dalle rappresentazioni in forma di stringa di tali oggetti.</span><span class="sxs-lookup"><span data-stu-id="7574e-417">Describes how to initialize objects to the values described by string representations of those objects.</span></span> <span data-ttu-id="7574e-418">L'analisi è l'operazione contraria alla formattazione.</span><span class="sxs-lookup"><span data-stu-id="7574e-418">Parsing is the inverse operation of formatting.</span></span>

## <a name="reference"></a><span data-ttu-id="7574e-419">Riferimento</span><span class="sxs-lookup"><span data-stu-id="7574e-419">Reference</span></span>

[<span data-ttu-id="7574e-420">System.IFormattable</span><span class="sxs-lookup"><span data-stu-id="7574e-420">System.IFormattable</span></span>](xref:System.IFormattable)

[<span data-ttu-id="7574e-421">System.IFormatProvider</span><span class="sxs-lookup"><span data-stu-id="7574e-421">System.IFormatProvider</span></span>](xref:System.IFormatProvider)

[<span data-ttu-id="7574e-422">System.ICustomFormatter</span><span class="sxs-lookup"><span data-stu-id="7574e-422">System.ICustomFormatter</span></span>](xref:System.ICustomFormatter)

