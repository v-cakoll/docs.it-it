---
title: 'File XML di esempio: configurazione di test in uno spazio dei nomi1'
ms.date: 07/20/2015
ms.assetid: e75ad1bc-5636-4623-9a34-a286a8c485d6
ms.openlocfilehash: 975e0bdfe22758b968dde4e97cf5b302579a7ca7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589243"
---
# <a name="sample-xml-file-test-configuration-in-a-namespace"></a><span data-ttu-id="e3451-102">File XML di esempio: configurazione di test in uno spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="e3451-102">Sample XML File: Test Configuration in a Namespace</span></span>
<span data-ttu-id="e3451-103">Il file XML seguente viene usato in vari esempi nella documentazione di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3451-103">The following XML file is used in various examples in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] documentation.</span></span> <span data-ttu-id="e3451-104">Si tratta di un file di configurazione di test.</span><span class="sxs-lookup"><span data-stu-id="e3451-104">This is a test configuration file.</span></span> <span data-ttu-id="e3451-105">L'XML si trova in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e3451-105">The XML is in a namespace.</span></span>  
  
## <a name="testconfiginnamespacexml"></a><span data-ttu-id="e3451-106">TestConfigInNamespace.xml</span><span class="sxs-lookup"><span data-stu-id="e3451-106">TestConfigInNamespace.xml</span></span>  
  
```xml  
<?xml version="1.0"?>  
<Tests xmlns="http://www.adatum.com">  
  <Test TestId="0001" TestType="CMD">  
    <Name>Convert number to string</Name>  
    <CommandLine>Examp1.EXE</CommandLine>  
    <Input>1</Input>  
    <Output>One</Output>  
  </Test>  
  <Test TestId="0002" TestType="CMD">  
    <Name>Find succeeding characters</Name>  
    <CommandLine>Examp2.EXE</CommandLine>  
    <Input>abc</Input>  
    <Output>def</Output>  
  </Test>  
  <Test TestId="0003" TestType="GUI">  
    <Name>Convert multiple numbers to strings</Name>  
    <CommandLine>Examp2.EXE /Verbose</CommandLine>  
    <Input>123</Input>  
    <Output>One Two Three</Output>  
  </Test>  
  <Test TestId="0004" TestType="GUI">  
    <Name>Find correlated key</Name>  
    <CommandLine>Examp3.EXE</CommandLine>  
    <Input>a1</Input>  
    <Output>b1</Output>  
  </Test>  
  <Test TestId="0005" TestType="GUI">  
    <Name>Count characters</Name>  
    <CommandLine>FinalExamp.EXE</CommandLine>  
    <Input>This is a test</Input>  
    <Output>14</Output>  
  </Test>  
  <Test TestId="0006" TestType="GUI">  
    <Name>Another Test</Name>  
    <CommandLine>Examp2.EXE</CommandLine>  
    <Input>Test Input</Input>  
    <Output>10</Output>  
  </Test>  
</Tests>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e3451-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3451-107">See also</span></span>

- [<span data-ttu-id="e3451-108">Documenti XML di esempio (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="e3451-108">Sample XML Documents (LINQ to XML)</span></span>](../../../../csharp/programming-guide/concepts/linq/sample-xml-documents-linq-to-xml.md)
