---
title: Creazione di nuove stringhe in .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CopyTo method
- Join method
- Format method
- Concat method
- strings [.NET Framework], creating
- Insert method
ms.assetid: 06fdf123-2fac-4459-8904-eb48ab908a30
ms.openlocfilehash: a5dfe6429ac135202874f0524a252a7af900bd8d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84279012"
---
# <a name="creating-new-strings-in-net"></a><span data-ttu-id="4e834-102">Creazione di nuove stringhe in .NET</span><span class="sxs-lookup"><span data-stu-id="4e834-102">Creating New Strings in .NET</span></span>
<span data-ttu-id="4e834-103">.NET Framework consente di creare stringhe usando una semplice assegnazione, oltre a eseguire l'overload del costruttore di classe per supportare la creazione di stringhe tramite una serie di parametri diversi.</span><span class="sxs-lookup"><span data-stu-id="4e834-103">The .NET Framework allows strings to be created using simple assignment, and also overloads a class constructor to support string creation using a number of different parameters.</span></span> <span data-ttu-id="4e834-104">.NET Framework offre anche diversi metodi nella classe <xref:System.String?displayProperty=nameWithType> per creare nuovi oggetti stringa combinando più stringhe, matrici di stringhe o oggetti.</span><span class="sxs-lookup"><span data-stu-id="4e834-104">The .NET Framework also provides several methods in the <xref:System.String?displayProperty=nameWithType> class that create new string objects by combining several strings, arrays of strings, or objects.</span></span>  
  
## <a name="creating-strings-using-assignment"></a><span data-ttu-id="4e834-105">Creazione di stringhe tramite assegnazione</span><span class="sxs-lookup"><span data-stu-id="4e834-105">Creating Strings Using Assignment</span></span>  
 <span data-ttu-id="4e834-106">Il modo più semplice per creare un nuovo oggetto <xref:System.String> consiste nell'assegnare un valore letterale stringa a un oggetto <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="4e834-106">The easiest way to create a new <xref:System.String> object is simply to assign a string literal to a <xref:System.String> object.</span></span>  
  
## <a name="creating-strings-using-a-class-constructor"></a><span data-ttu-id="4e834-107">Creazione di stringhe tramite un costruttore di classe</span><span class="sxs-lookup"><span data-stu-id="4e834-107">Creating Strings Using a Class Constructor</span></span>  
 <span data-ttu-id="4e834-108">È possibile usare overload del costruttore della classe <xref:System.String> per creare stringhe da matrici di caratteri.</span><span class="sxs-lookup"><span data-stu-id="4e834-108">You can use overloads of the <xref:System.String> class constructor to create strings from character arrays.</span></span> <span data-ttu-id="4e834-109">È anche possibile creare una nuova stringa duplicando un determinato carattere per un numero specifico di volte.</span><span class="sxs-lookup"><span data-stu-id="4e834-109">You can also create a new string by duplicating a particular character a specified number of times.</span></span>  
  
## <a name="methods-that-return-strings"></a><span data-ttu-id="4e834-110">Metodi che restituiscono stringhe</span><span class="sxs-lookup"><span data-stu-id="4e834-110">Methods that Return Strings</span></span>  
 <span data-ttu-id="4e834-111">Nella tabella seguente sono elencati diversi metodi utili che restituiscono nuovi oggetti stringa.</span><span class="sxs-lookup"><span data-stu-id="4e834-111">The following table lists several useful methods that return new string objects.</span></span>  
  
|<span data-ttu-id="4e834-112">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="4e834-112">Method name</span></span>|<span data-ttu-id="4e834-113">Uso</span><span class="sxs-lookup"><span data-stu-id="4e834-113">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|<span data-ttu-id="4e834-114">Compila una stringa formattata da un insieme di oggetti di input.</span><span class="sxs-lookup"><span data-stu-id="4e834-114">Builds a formatted string from a set of input objects.</span></span>|  
|<xref:System.String.Concat%2A?displayProperty=nameWithType>|<span data-ttu-id="4e834-115">Compila stringhe da due o più stringhe.</span><span class="sxs-lookup"><span data-stu-id="4e834-115">Builds strings from two or more strings.</span></span>|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|<span data-ttu-id="4e834-116">Compila una nuova stringa combinando una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="4e834-116">Builds a new string by combining an array of strings.</span></span>|  
|<xref:System.String.Insert%2A?displayProperty=nameWithType>|<span data-ttu-id="4e834-117">Compila una nuova stringa inserendo una stringa in corrispondenza dell'indice specificato di una stringa esistente.</span><span class="sxs-lookup"><span data-stu-id="4e834-117">Builds a new string by inserting a string into the specified index of an existing string.</span></span>|  
|<xref:System.String.CopyTo%2A?displayProperty=nameWithType>|<span data-ttu-id="4e834-118">Copia i caratteri specificati di una stringa in una determinata posizione all'interno di una matrice di caratteri.</span><span class="sxs-lookup"><span data-stu-id="4e834-118">Copies specified characters in a string into a specified position in an array of characters.</span></span>|  
  
### <a name="format"></a><span data-ttu-id="4e834-119">Format</span><span class="sxs-lookup"><span data-stu-id="4e834-119">Format</span></span>  
 <span data-ttu-id="4e834-120">È possibile usare il metodo **String.Format** per creare stringhe formattate e concatenare stringhe che rappresentano più oggetti.</span><span class="sxs-lookup"><span data-stu-id="4e834-120">You can use the **String.Format** method to create formatted strings and concatenate strings representing multiple objects.</span></span> <span data-ttu-id="4e834-121">Qualsiasi oggetto venga passato a questo metodo viene automaticamente convertito in una stringa.</span><span class="sxs-lookup"><span data-stu-id="4e834-121">This method automatically converts any passed object into a string.</span></span> <span data-ttu-id="4e834-122">Se ad esempio l'applicazione deve visualizzare un valore **Int32** e un valore **DateTime**, è possibile costruire con facilità una stringa che rappresenti tali valori usando il metodo **Format**.</span><span class="sxs-lookup"><span data-stu-id="4e834-122">For example, if your application must display an **Int32** value and a **DateTime** value to the user, you can easily construct a string to represent these values using the **Format** method.</span></span> <span data-ttu-id="4e834-123">Per altre informazioni sulle convenzioni di formattazione usate con questo metodo, vedere la sezione relativa alla [formattazione composita](composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="4e834-123">For information about formatting conventions used with this method, see the section on [composite formatting](composite-formatting.md).</span></span>  
  
 <span data-ttu-id="4e834-124">L'esempio di codice seguente usa il metodo **Format** per creare una stringa che usa una variabile integer.</span><span class="sxs-lookup"><span data-stu-id="4e834-124">The following example uses the **Format** method to create a string that uses an integer variable.</span></span>  
  
 [!code-csharp[Strings.Creating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#1)]
 [!code-vb[Strings.Creating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#1)]  
  
 <span data-ttu-id="4e834-125">In questo esempio <xref:System.DateTime.Now%2A?displayProperty=nameWithType> visualizza l'ora e la data correnti nel modo specificato dalle impostazioni cultura associate al thread corrente.</span><span class="sxs-lookup"><span data-stu-id="4e834-125">In this example,<xref:System.DateTime.Now%2A?displayProperty=nameWithType> displays the current date and time in a manner specified by the culture associated with the current thread.</span></span>  
  
### <a name="concat"></a><span data-ttu-id="4e834-126">Concat</span><span class="sxs-lookup"><span data-stu-id="4e834-126">Concat</span></span>  
 <span data-ttu-id="4e834-127">Il metodo **String.Concat** può essere usato per creare facilmente un nuovo oggetto stringa da due o più oggetti esistenti.</span><span class="sxs-lookup"><span data-stu-id="4e834-127">The **String.Concat** method can be used to easily create a new string object from two or more existing objects.</span></span> <span data-ttu-id="4e834-128">Questo metodo rappresenta una modalità di concatenamento delle stringhe indipendente dal linguaggio.</span><span class="sxs-lookup"><span data-stu-id="4e834-128">It provides a language-independent way to concatenate strings.</span></span> <span data-ttu-id="4e834-129">Il metodo accetta qualsiasi classe derivi da **System.Object**.</span><span class="sxs-lookup"><span data-stu-id="4e834-129">This method accepts any class that derives from **System.Object**.</span></span> <span data-ttu-id="4e834-130">Nell'esempio di codice che segue viene creata una stringa da due oggetti stringa esistenti e da un carattere di separazione.</span><span class="sxs-lookup"><span data-stu-id="4e834-130">The following example creates a string from two existing string objects and a separating character.</span></span>  
  
 [!code-csharp[Strings.Creating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#2)]
 [!code-vb[Strings.Creating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#2)]  
  
### <a name="join"></a><span data-ttu-id="4e834-131">Join</span><span class="sxs-lookup"><span data-stu-id="4e834-131">Join</span></span>  
 <span data-ttu-id="4e834-132">Il metodo **String.Join** consente di creare una nuova stringa da una matrice di stringhe e da una stringa di separazione.</span><span class="sxs-lookup"><span data-stu-id="4e834-132">The **String.Join** method creates a new string from an array of strings and a separator string.</span></span> <span data-ttu-id="4e834-133">Questo metodo è utile per concatenare più stringhe, creando un elenco, eventualmente separato da virgole.</span><span class="sxs-lookup"><span data-stu-id="4e834-133">This method is useful if you want to concatenate multiple strings together, making a list perhaps separated by a comma.</span></span>  
  
 <span data-ttu-id="4e834-134">Nell'esempio di codice seguente viene usato uno spazio per eseguire l'associazione di una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="4e834-134">The following example uses a space to bind a string array.</span></span>  
  
 [!code-csharp[Strings.Creating#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#3)]
 [!code-vb[Strings.Creating#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#3)]  
  
### <a name="insert"></a><span data-ttu-id="4e834-135">Insert</span><span class="sxs-lookup"><span data-stu-id="4e834-135">Insert</span></span>  
 <span data-ttu-id="4e834-136">Il metodo **String.Insert** consente di creare una nuova stringa inserendo una stringa in una posizione specificata in un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="4e834-136">The **String.Insert** method creates a new string by inserting a string into a specified position in another string.</span></span> <span data-ttu-id="4e834-137">Questo metodo usa un indice a base zero.</span><span class="sxs-lookup"><span data-stu-id="4e834-137">This method uses a zero-based index.</span></span> <span data-ttu-id="4e834-138">Nell'esempio di codice che segue viene inserita una stringa in corrispondenza della quinta posizione di indice di `MyString` e viene creata una nuova stringa con tale valore.</span><span class="sxs-lookup"><span data-stu-id="4e834-138">The following example inserts a string into the fifth index position of `MyString` and creates a new string with this value.</span></span>  
  
 [!code-csharp[Strings.Creating#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#4)]
 [!code-vb[Strings.Creating#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#4)]  
  
### <a name="copyto"></a><span data-ttu-id="4e834-139">CopyTo</span><span class="sxs-lookup"><span data-stu-id="4e834-139">CopyTo</span></span>  
 <span data-ttu-id="4e834-140">Il metodo **String.CopyTo** consente di copiare parti di una stringa in una matrice di caratteri.</span><span class="sxs-lookup"><span data-stu-id="4e834-140">The **String.CopyTo** method copies portions of a string into an array of characters.</span></span> <span data-ttu-id="4e834-141">È possibile specificare sia l'indice iniziale della stringa sia il numero dei caratteri da copiare.</span><span class="sxs-lookup"><span data-stu-id="4e834-141">You can specify both the beginning index of the string and the number of characters to be copied.</span></span> <span data-ttu-id="4e834-142">Il metodo contiene l'indice di origine, una matrice di caratteri, l'indice di destinazione e il numero dei caratteri da copiare.</span><span class="sxs-lookup"><span data-stu-id="4e834-142">This method takes the source index, an array of characters, the destination index, and the number of characters to copy.</span></span> <span data-ttu-id="4e834-143">Tutti gli indici sono a base zero.</span><span class="sxs-lookup"><span data-stu-id="4e834-143">All indexes are zero-based.</span></span>  
  
 <span data-ttu-id="4e834-144">Nell'esempio di codice riportato di seguito il metodo **CopyTo** viene usato per copiare nella prima posizione di indice di una matrice di caratteri i caratteri della parola "Hello" di un oggetto stringa.</span><span class="sxs-lookup"><span data-stu-id="4e834-144">The following example uses the **CopyTo** method to copy the characters of the word "Hello" from a string object to the first index position of an array of characters.</span></span>  
  
 [!code-csharp[Strings.Creating#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#5)]
 [!code-vb[Strings.Creating#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="4e834-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e834-145">See also</span></span>

- [<span data-ttu-id="4e834-146">Operazioni di base sulle stringhe</span><span class="sxs-lookup"><span data-stu-id="4e834-146">Basic String Operations</span></span>](basic-string-operations.md)
- [<span data-ttu-id="4e834-147">Formattazione composita</span><span class="sxs-lookup"><span data-stu-id="4e834-147">Composite Formatting</span></span>](composite-formatting.md)
