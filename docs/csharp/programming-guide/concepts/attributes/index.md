---
title: Attributi (C#)
ms.date: 04/26/2018
ms.openlocfilehash: 0379bb76cf18ff836bd14aafb9cb97c30aee8ec7
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645480"
---
# <a name="attributes-c"></a>Attributi (C#)

Gli attributi offrono un metodo efficace per l'associazione di metadati o informazioni dichiarative con il codice (assembly, tipi, metodi, proprietà e così via). Dopo aver associato un attributo a un'entità di programma, in fase di esecuzione è possibile eseguire una query su tale attributo usando una tecnica denominata *reflection*. Per altre informazioni, vedere [Reflection (C#)](../reflection.md).

Di seguito sono riportate le proprietà degli attributi:

- Gli attributi aggiungono metadati al programma. I *metadati* sono informazioni relative ai tipi definiti in un programma. Tutti gli assembly .NET contengono un set specificato di metadati che descrive i tipi e membri dei tipi definiti nell'assembly. È possibile aggiungere attributi personalizzati per specificare altre informazioni eventualmente necessarie. Per altre informazioni, vedere [Creazione di attributi personalizzati (C#)](creating-custom-attributes.md).
- È possibile applicare uno o più attributi a interi assembly, moduli o elementi di programma di minori dimensioni, ad esempio classi e proprietà.
- Gli attributi possono accettare argomenti nello stesso modo dei metodi e delle proprietà.
- Il programma può esaminare i propri metadati oppure i metadati di un altro programma tramite reflection. Per altre informazioni, vedere [Accesso agli attributi tramite reflection (C#)](accessing-attributes-by-using-reflection.md).

## <a name="using-attributes"></a>Utilizzo di attributi

È possibile usare attributi nella maggior parte delle dichiarazioni, anche se la validità di un attributo specifico può essere limitata ad alcuni tipi di dichiarazione. Per specificare un attributo in C# inserire il nome dell'attributo racchiuso tra parentesi quadre ([]) sopra la dichiarazione dell'entità a cui è applicato.

Nell'esempio seguente l'attributo <xref:System.SerializableAttribute> viene usato per applicare una caratteristica specifica a una classe:

[!code-csharp[Using the serializable attribute](~/samples/snippets/csharp/attributes/AttributesOverview.cs#1)]

Un metodo con l'attributo <xref:System.Runtime.InteropServices.DllImportAttribute> è dichiarato come nell'esempio seguente:

[!code-csharp[Declaring a method to import from an external library](../../../../../samples/snippets/csharp/attributes/AttributesOverview.cs#2)]

In una dichiarazione è possibile inserire più attributi, come illustrato nell'esempio seguente:

[!code-csharp[Including the interop namespace](~/samples/snippets/csharp/attributes/AttributesOverview.cs#3)]
[!code-csharp[Declaring two way marshaling for arguments](~/samples/snippets/csharp/attributes/AttributesOverview.cs#4)]

Alcuni attributi possono essere specificati più volte per una stessa entità. Un esempio di attributo multiuso è <xref:System.Diagnostics.ConditionalAttribute>:

[!code-csharp[Using the conditional attribute](~/samples/snippets/csharp/attributes/AttributesOverview.cs#5)]

> [!NOTE]
> Per convenzione tutti i nomi di attributo terminano con la parola "Attribute", in modo che sia possibile distinguerli da altri elementi delle librerie .NET. Tuttavia, quando gli attributi vengono usati nel codice, non è necessario specificare il suffisso Attribute. Ad esempio `[DllImport]` è equivalente a `[DllImportAttribute]`, mentre `DllImportAttribute` è il nome effettivo dell'attributo nella libreria di classi .NET Framework.

### <a name="attribute-parameters"></a>Parametri degli attributi

Diversi attributi dispongono di parametri, che possono essere posizionali, senza nome o denominati. I parametri posizionali devono essere specificati in un determinato ordine e non possono essere omessi. I parametri denominati sono facoltativi e possono essere specificati in qualsiasi ordine. I parametri posizionali vengono specificati per primi. I tre attributi seguenti, ad esempio, sono equivalenti:

```csharp
[DllImport("user32.dll")]
[DllImport("user32.dll", SetLastError=false, ExactSpelling=false)]
[DllImport("user32.dll", ExactSpelling=false, SetLastError=false)]
```

Il primo parametro, ovvero il nome della DLL, è posizionale ed è sempre specificato per primo. Gli altri parametri sono denominati. In questo caso, entrambi i parametri denominati sono impostati automaticamente su false e possono quindi essere omessi. I parametri posizionali corrispondono ai parametri del costruttore dell'attributo. I parametri denominati o facoltativi corrispondono a proprietà o campi dell'attributo. Per informazioni sui valori predefiniti dei parametri, fare riferimento alla documentazione di ciascun attributo.

### <a name="attribute-targets"></a>Destinazioni degli attributi

La *destinazione* di un attributo è l'entità a cui tale attributo viene applicato. Un attributo, ad esempio, può essere applicato a una classe, a un metodo particolare o a un intero assembly. Per impostazione predefinita, un attributo si applica all'elemento che lo segue. È tuttavia possibile identificare in modo esplicito, ad esempio, se un attributo viene applicato a un metodo, al relativo parametro o al relativo valore restituito.

Per identificare in modo esplicito la destinazione di un attributo, usare la sintassi seguente:

```csharp
[target : attribute-list]
```

Nella tabella seguente sono elencati i possibili valori di `target`.

|Valore di destinazione|Si applica a|
|------------------|----------------|
|`assembly`|Intero assembly|
|`module`|Modulo di assembly corrente|
|`field`|Campo in una classe o uno struct|
|`event`|Event|
|`method`|Metodo o funzioni di accesso alle proprietà `get` e `set`|
|`param`|Parametri del metodo o parametri della funzione di accesso alla proprietà `set`|
|`property`|Proprietà|
|`return`|Valore restituito di un metodo, un indicizzatore di proprietà o una funzione di accesso alla proprietà `get`|
|`type`|Struct, classe, interfaccia, enumeratore o delegato|

È necessario specificare il valore di destinazione `field` per applicare un attributo al campo sottostante creato per una [proprietà implementata automaticamente](../../../properties.md).

Nell'esempio seguente viene illustrato come applicare attributi ad assembly e moduli. Per altre informazioni, vedere [Attributi comuni (C#)](../../../language-reference/attributes/global.md).

```csharp
using System;
using System.Reflection;
[assembly: AssemblyTitleAttribute("Production assembly 4")]
[module: CLSCompliant(true)]
```

Nell'esempio seguente viene illustrato come applicare gli attributi a metodi, parametri di metodo e valori restituiti dal metodo in C#.

[!code-csharp[Applying attributes to different code elements](../../../../../samples/snippets/csharp/attributes/AttributesOverview.cs#6)]

> [!NOTE]
> Indipendentemente dalle destinazioni in cui l'oggetto `ValidatedContract` è definito come valido, è necessario specificare la destinazione `return`, anche se `ValidatedContract` viene definito in modo da essere valido solo per i valori restituiti. In altre parole, il compilatore non usa le informazioni `AttributeUsage` per risolvere le destinazioni degli attributi ambigue. Per altre informazioni, vedere [AttributeUsage (C#)](../../../language-reference/attributes/general.md).

## <a name="common-uses-for-attributes"></a>Usi comuni degli attributi

Di seguito vengono elencati alcuni degli usi comuni degli attributi nel codice:

- Contrassegno dei metodi mediante l'attributo `WebMethod` nei servizi Web per indicare che è possibile chiamare il metodo tramite il protocollo SOAP. Per altre informazioni, vedere <xref:System.Web.Services.WebMethodAttribute>.
- Descrizione della procedura di marshalling dei parametri del metodo durante l'interazione con il codice nativo. Per altre informazioni, vedere <xref:System.Runtime.InteropServices.MarshalAsAttribute>.
- Descrizione delle proprietà COM per classi, metodi e interfacce.
- Chiamata al codice non gestito che usa la classe <xref:System.Runtime.InteropServices.DllImportAttribute>.
- Descrizione dell'assembly con indicazione di titolo, versione, descrizione o marchio.
- Descrizione dei membri della classe da serializzare per la persistenza.
- Descrizione della procedura di mapping tra membri di una classe e nodi XML per la serializzazione XML.
- Descrizione dei requisiti di sicurezza per i metodi.
- Definizione delle caratteristiche usate per garantire la sicurezza.
- Controllo delle ottimizzazioni tramite il compilatore JIT (Just-In-Time), in modo da garantire un semplice debug del codice.
- Recupero di informazioni relative al chiamante di un metodo.

## <a name="related-sections"></a>Sezioni correlate

Per altre informazioni, vedere:

- [Creazione di attributi personalizzati (C#)](creating-custom-attributes.md)  
- [Accessing Attributes by Using Reflection (C#)](accessing-attributes-by-using-reflection.md) (Accesso agli attributi con reflection (C#))  
- [Come creare un'unione C/C](how-to-create-a-c-cpp-union-by-using-attributes.md)  
- [Attributi comuni (C#)](../../../language-reference/attributes/global.md)  
- [Informazioni sul chiamante (C#)](../../../language-reference/attributes/caller-information.md)  

## <a name="see-also"></a>Vedere anche

- [Guida alla programmazione in C](../../index.md)
- [Reflection (C#)](../reflection.md)
- [Attributi](../../../../standard/attributes/index.md)
- [Uso degli attributi in C#](../../../tutorials/attributes.md)
