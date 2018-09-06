---
title: Utilizzo dell'attività Switch con tipi personalizzati
ms.date: 03/30/2017
ms.assetid: 482a48c4-eb83-40c3-a4e2-2f9a8af88b75
ms.openlocfilehash: b24a03573b31f3fb1c34d4aa6e03bc11f5b25455
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "44038874"
---
# <a name="usage-of-the-switch-activity-with-custom-types"></a><span data-ttu-id="03f33-102">Utilizzo dell'attività Switch con tipi personalizzati</span><span class="sxs-lookup"><span data-stu-id="03f33-102">Usage of the Switch Activity with Custom Types</span></span>
<span data-ttu-id="03f33-103">In questo esempio viene descritto come consentire a un'attività <xref:System.Activities.Statements.Switch%601> di valutare un tipo complesso definito dall'utente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="03f33-103">This sample describes how to enable a <xref:System.Activities.Statements.Switch%601> activity to evaluate a user-defined complex type at runtime.</span></span> <span data-ttu-id="03f33-104">Nei linguaggi di programmazione procedurali più tradizionali, un' [commutatore](https://go.microsoft.com/fwlink/?LinkId=180521) istruzione seleziona una logica di esecuzione in base alla valutazione condizionale di una variabile.</span><span class="sxs-lookup"><span data-stu-id="03f33-104">In most traditional procedural programming languages, a [switch](https://go.microsoft.com/fwlink/?LinkId=180521) statement selects an execution logic based on the conditional evaluation of a variable.</span></span> <span data-ttu-id="03f33-105">Tradizionalmente, un'istruzione `switch` agisce su un'espressione che può essere valutata staticamente.</span><span class="sxs-lookup"><span data-stu-id="03f33-105">Traditionally, a `switch` statement operates on an expression that can be statically evaluated.</span></span> <span data-ttu-id="03f33-106">Ad esempio, in C# ciò significa che sono supportati solo tipi primitivi, quali <xref:System.Boolean>, <xref:System.Int32>, <xref:System.String>, e tipi di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="03f33-106">For example, in C# this means that only primitive types, such as <xref:System.Boolean>, <xref:System.Int32>, <xref:System.String>, and enumeration types are supported.</span></span>  
  
 <span data-ttu-id="03f33-107">Per abilitare il passaggio in una classe personalizzata, è necessario implementare la logica per valutare valori di tipo complesso personalizzato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="03f33-107">To enable switching on a custom class, logic must be implemented to evaluate values of the custom complex type at runtime.</span></span> <span data-ttu-id="03f33-108">In questo esempio viene illustrato come abilitare il passaggio su un tipo complesso personalizzato denominato `Person`.</span><span class="sxs-lookup"><span data-stu-id="03f33-108">This sample demonstrates how to enable switching on a custom complex type named `Person`.</span></span>  
  
-   <span data-ttu-id="03f33-109">Nella classe personalizzata `Person` un attributo <xref:System.ComponentModel.TypeConverter> viene dichiarato con il nome dell'oggetto <xref:System.ComponentModel.TypeConverter> personalizzato.</span><span class="sxs-lookup"><span data-stu-id="03f33-109">In the custom class `Person`, a <xref:System.ComponentModel.TypeConverter> attribute is declared with the name of the custom <xref:System.ComponentModel.TypeConverter>.</span></span>  
  
    ```  
    [TypeConverter(typeof(PersonConverter))]  
    public class Person  
    {  
       public string Name { get; set; }  
       public int Age { get; set; }  
    ...  
    ```  
  
-   <span data-ttu-id="03f33-110">Nella classe personalizzata `Person` viene eseguito l'override delle classi <xref:System.Object.Equals%2A> e <xref:System.Object.GetHashCode%2A>.</span><span class="sxs-lookup"><span data-stu-id="03f33-110">In the custom class `Person`, the <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> classes are overridden.</span></span>  
  
    ```  
    public override bool Equals(object obj)  
    {  
        Person person = obj as Person;  
  
        if (person != null)  
        {  
            return string.Equals(this.Name, person.Name);  
        }  
  
        return false;  
    }  
  
    public override int GetHashCode()  
    {  
        if (this.Name != null)  
        {  
            return this.Name.GetHashCode();  
        }  
  
        return 0;  
    }  
    ```  
  
-   <span data-ttu-id="03f33-111">Viene implementata una classe personalizzata <xref:System.ComponentModel.TypeConverter> che esegue la conversione di un'istanza della classe personalizzata in una stringa e una stringa in un'istanza di una classe personalizzata.</span><span class="sxs-lookup"><span data-stu-id="03f33-111">A custom <xref:System.ComponentModel.TypeConverter> class is implemented that performs the conversion of an instance of the custom class to a string and a string to an instance of a custom class.</span></span>  
  
    ```  
    public class PersonConverter : TypeConverter  
    {  
        public override bool CanConvertFrom(ITypeDescriptorContext context,  
           Type sourceType)  
        {  
            return (sourceType is string);  
        }  
  
        // Overrides the ConvertFrom method of TypeConverter.  
        public override object ConvertFrom(ITypeDescriptorContext context,  
           CultureInfo culture, object value)  
        {  
            if (value == null)  
            {  
                return null;  
            }  
  
            if (value is string)  
            {  
                return new Person  
                {  
                    Name = (string)value  
                };  
            }  
  
            return base.ConvertFrom(context, culture, value);  
        }  
  
        // Overrides the ConvertTo method of TypeConverter.  
        public override object ConvertTo(ITypeDescriptorContext context,  
           CultureInfo culture, object value, Type destinationType)  
        {  
            if (destinationType == typeof(string))  
            {  
                if (value != null)  
                {  
                    return ((Person) value).Name;  
                }  
                else  
                {  
                    return null;  
                }  
            }  
  
            return base.ConvertTo(context, culture, value, destinationType);  
        }  
    }  
    ```  
  
 <span data-ttu-id="03f33-112">In questo esempio sono inclusi i file seguenti:</span><span class="sxs-lookup"><span data-stu-id="03f33-112">The following files are included in this sample:</span></span>  
  
-   <span data-ttu-id="03f33-113">**Person.cs**: definisce il `Person` classe.</span><span class="sxs-lookup"><span data-stu-id="03f33-113">**Person.cs**: Defines the `Person` class.</span></span>  
  
-   <span data-ttu-id="03f33-114">**PersonConverter.cs**: il convertitore di tipi per il `Person` classe.</span><span class="sxs-lookup"><span data-stu-id="03f33-114">**PersonConverter.cs**: The type converter for the `Person` class.</span></span>  
  
-   <span data-ttu-id="03f33-115">**Sequence**: un flusso di lavoro che passa il `Person` tipo.</span><span class="sxs-lookup"><span data-stu-id="03f33-115">**Sequence.xaml**: a workflow that switches over the `Person` type.</span></span>  
  
-   <span data-ttu-id="03f33-116">**Program.cs**: la funzione principale che esegue il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="03f33-116">**Program.cs**: The main function that runs the workflow.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="03f33-117">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="03f33-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="03f33-118">Caricare Switch.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03f33-118">Load Switch.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="03f33-119">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="03f33-119">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="03f33-120">Premere CTRL + F5 per eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="03f33-120">Press CTRL + F5 to run the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="03f33-121">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="03f33-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="03f33-122">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="03f33-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="03f33-123">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="03f33-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="03f33-124">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="03f33-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Switch`  
  
## <a name="see-also"></a><span data-ttu-id="03f33-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03f33-125">See Also</span></span>  
 [<span data-ttu-id="03f33-126">Libreria di attività incorporata</span><span class="sxs-lookup"><span data-stu-id="03f33-126">Built-In Activity Library</span></span>](../../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md)
