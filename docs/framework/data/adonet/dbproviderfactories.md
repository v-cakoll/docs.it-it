---
title: Oggetti DbProviderFactory
ms.date: 03/30/2017
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
ms.openlocfilehash: e3ea9e3d083314f8df25f9edadbd1a18f1227293
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784097"
---
# <a name="dbproviderfactories"></a><span data-ttu-id="1cfb3-102">Oggetti DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="1cfb3-102">DbProviderFactories</span></span>
<span data-ttu-id="1cfb3-103">Lo spazio dei nomi <xref:System.Data.Common> fornisce classi per la creazione di istanze di <xref:System.Data.Common.DbProviderFactory> per l'uso di origini dati specifiche.</span><span class="sxs-lookup"><span data-stu-id="1cfb3-103">The <xref:System.Data.Common> namespace provides classes for creating <xref:System.Data.Common.DbProviderFactory> instances to work with specific data sources.</span></span> <span data-ttu-id="1cfb3-104">Quando si crea un'istanza di <xref:System.Data.Common.DbProviderFactory> e si passano le informazioni sul provider di dati, `DbProviderFactory` è in grado di determinare l'oggetto connessione corretto, fortemente tipizzato, da restituire in base alle informazioni fornite.</span><span class="sxs-lookup"><span data-stu-id="1cfb3-104">When you create a <xref:System.Data.Common.DbProviderFactory> instance and pass it information about the data provider, the `DbProviderFactory` can determine the correct, strongly typed connection object to return based on the information it has been provided.</span></span>  
  
 <span data-ttu-id="1cfb3-105">A partire dalla versione 4 di .NET Framework, i provider di dati come <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient> e <xref:System.Data.OracleClient>, a differenza dei provider personalizzati, non vengono più elencati nel file machine.config.</span><span class="sxs-lookup"><span data-stu-id="1cfb3-105">Beginning in the .NET Framework version 4, data providers such as <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient>, and <xref:System.Data.OracleClient> are no longer listed in machine.config file, but custom providers will continue to be listed there.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1cfb3-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="1cfb3-106">In This Section</span></span>  
 [<span data-ttu-id="1cfb3-107">Panoramica del modello Factory</span><span class="sxs-lookup"><span data-stu-id="1cfb3-107">Factory Model Overview</span></span>](factory-model-overview.md)  
 <span data-ttu-id="1cfb3-108">Viene fornita una panoramica del modello di progettazione e dell'interfaccia di programmazione di factory.</span><span class="sxs-lookup"><span data-stu-id="1cfb3-108">Provides an overview of the factory design pattern and programming interface.</span></span>  
  
 [<span data-ttu-id="1cfb3-109">Recupero di una classe DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="1cfb3-109">Obtaining a DbProviderFactory</span></span>](obtaining-a-dbproviderfactory.md)  
 <span data-ttu-id="1cfb3-110">Viene illustrato come elencare i provider di dati installati e creare un oggetto <xref:System.Data.Common.DbConnection> da `DbProviderFactory`.</span><span class="sxs-lookup"><span data-stu-id="1cfb3-110">Demonstrates how to list the installed data providers and create a <xref:System.Data.Common.DbConnection> from a `DbProviderFactory`.</span></span>  
  
 [<span data-ttu-id="1cfb3-111">DbConnection, DbCommand e DbException</span><span class="sxs-lookup"><span data-stu-id="1cfb3-111">DbConnection, DbCommand and DbException</span></span>](dbconnection-dbcommand-and-dbexception.md)  
 <span data-ttu-id="1cfb3-112">Viene illustrato come creare oggetti <xref:System.Data.Common.DbCommand> e <xref:System.Data.Common.DbDataReader> nonché come gestire gli errori di dati tramite <xref:System.Data.Common.DbException>.</span><span class="sxs-lookup"><span data-stu-id="1cfb3-112">Demonstrates how to create a <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbDataReader>, and how to handle data errors using <xref:System.Data.Common.DbException>.</span></span>  
  
 [<span data-ttu-id="1cfb3-113">Modifica di dati con un oggetto DbDataAdapter</span><span class="sxs-lookup"><span data-stu-id="1cfb3-113">Modifying Data with a DbDataAdapter</span></span>](modifying-data-with-a-dbdataadapter.md)  
 <span data-ttu-id="1cfb3-114">Viene illustrato come usare <xref:System.Data.Common.DbCommandBuilder> con <xref:System.Data.Common.DbDataAdapter> per recuperare e modificare dati.</span><span class="sxs-lookup"><span data-stu-id="1cfb3-114">Demonstrates how to use a <xref:System.Data.Common.DbCommandBuilder> with a <xref:System.Data.Common.DbDataAdapter> to retrieve and modify data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cfb3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cfb3-115">See also</span></span>

- [<span data-ttu-id="1cfb3-116">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1cfb3-116">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="1cfb3-117">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1cfb3-117">ADO.NET Overview</span></span>](ado-net-overview.md)
