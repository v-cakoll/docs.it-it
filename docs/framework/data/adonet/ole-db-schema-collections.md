---
title: Raccolte di schemi OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: f753f35aab0a0200da5de463a73abb9813253d11
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658455"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="9d8fc-102">Raccolte di schemi OLE DB</span><span class="sxs-lookup"><span data-stu-id="9d8fc-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="9d8fc-103">Contenuto della sezione viene descritto il supporto delle raccolte di schemi per i provider OLE DB per Microsoft SQL Server, Oracle e Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="9d8fc-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="9d8fc-104">Provider OLE DB per Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="9d8fc-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="9d8fc-105">Il Driver OLE DB Microsoft SQL Server supporta le seguenti raccolte di schemi specifici oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="9d8fc-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="9d8fc-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="9d8fc-106">Tables</span></span>  
  
-   <span data-ttu-id="9d8fc-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="9d8fc-107">Columns</span></span>  
  
-   <span data-ttu-id="9d8fc-108">Procedure</span><span class="sxs-lookup"><span data-stu-id="9d8fc-108">Procedures</span></span>  
  
-   <span data-ttu-id="9d8fc-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9d8fc-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="9d8fc-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="9d8fc-110">Catalog</span></span>  
  
-   <span data-ttu-id="9d8fc-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="9d8fc-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="9d8fc-112">Tabelle</span><span class="sxs-lookup"><span data-stu-id="9d8fc-112">Tables</span></span>  
  
|<span data-ttu-id="9d8fc-113">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d8fc-113">ColumnName</span></span>|<span data-ttu-id="9d8fc-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d8fc-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d8fc-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-115">TABLE_CATALOG</span></span>|<span data-ttu-id="9d8fc-116">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-116">String</span></span>|  
|<span data-ttu-id="9d8fc-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="9d8fc-118">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-118">String</span></span>|  
|<span data-ttu-id="9d8fc-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-119">TABLE_NAME</span></span>|<span data-ttu-id="9d8fc-120">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-120">String</span></span>|  
|<span data-ttu-id="9d8fc-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-121">TABLE_TYPE</span></span>|<span data-ttu-id="9d8fc-122">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-122">String</span></span>|  
|<span data-ttu-id="9d8fc-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-123">TABLE_GUID</span></span>|<span data-ttu-id="9d8fc-124">Guid</span><span class="sxs-lookup"><span data-stu-id="9d8fc-124">Guid</span></span>|  
|<span data-ttu-id="9d8fc-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-125">DESCRIPTION</span></span>|<span data-ttu-id="9d8fc-126">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-126">String</span></span>|  
|<span data-ttu-id="9d8fc-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-127">TABLE_PROPID</span></span>|<span data-ttu-id="9d8fc-128">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-128">Int64</span></span>|  
|<span data-ttu-id="9d8fc-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9d8fc-129">DATE_CREATED</span></span>|<span data-ttu-id="9d8fc-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d8fc-130">DateTime</span></span>|  
|<span data-ttu-id="9d8fc-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9d8fc-131">DATE_MODIFIED</span></span>|<span data-ttu-id="9d8fc-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d8fc-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="9d8fc-133">Colonne</span><span class="sxs-lookup"><span data-stu-id="9d8fc-133">Columns</span></span>  
  
|<span data-ttu-id="9d8fc-134">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d8fc-134">ColumnName</span></span>|<span data-ttu-id="9d8fc-135">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d8fc-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d8fc-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-136">TABLE_CATALOG</span></span>|<span data-ttu-id="9d8fc-137">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-137">String</span></span>|  
|<span data-ttu-id="9d8fc-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="9d8fc-139">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-139">String</span></span>|  
|<span data-ttu-id="9d8fc-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-140">TABLE_NAME</span></span>|<span data-ttu-id="9d8fc-141">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-141">String</span></span>|  
|<span data-ttu-id="9d8fc-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-142">COLUMN_NAME</span></span>|<span data-ttu-id="9d8fc-143">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-143">String</span></span>|  
|<span data-ttu-id="9d8fc-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-144">COLUMN_GUID</span></span>|<span data-ttu-id="9d8fc-145">Guid</span><span class="sxs-lookup"><span data-stu-id="9d8fc-145">Guid</span></span>|  
|<span data-ttu-id="9d8fc-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-146">COLUMN_PROPID</span></span>|<span data-ttu-id="9d8fc-147">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-147">Int64</span></span>|  
|<span data-ttu-id="9d8fc-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d8fc-149">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-149">Int64</span></span>|  
|<span data-ttu-id="9d8fc-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="9d8fc-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="9d8fc-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-151">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="9d8fc-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="9d8fc-153">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-153">String</span></span>|  
|<span data-ttu-id="9d8fc-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="9d8fc-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="9d8fc-155">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-155">Int64</span></span>|  
|<span data-ttu-id="9d8fc-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-156">IS_NULLABLE</span></span>|<span data-ttu-id="9d8fc-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-157">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-158">DATA_TYPE</span></span>|<span data-ttu-id="9d8fc-159">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-159">Int32</span></span>|  
|<span data-ttu-id="9d8fc-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-160">TYPE_GUID</span></span>|<span data-ttu-id="9d8fc-161">Guid</span><span class="sxs-lookup"><span data-stu-id="9d8fc-161">Guid</span></span>|  
|<span data-ttu-id="9d8fc-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d8fc-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9d8fc-163">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-163">Int64</span></span>|  
|<span data-ttu-id="9d8fc-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d8fc-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9d8fc-165">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-165">Int64</span></span>|  
|<span data-ttu-id="9d8fc-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9d8fc-167">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-167">Int32</span></span>|  
|<span data-ttu-id="9d8fc-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="9d8fc-169">Int16</span><span class="sxs-lookup"><span data-stu-id="9d8fc-169">Int16</span></span>|  
|<span data-ttu-id="9d8fc-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="9d8fc-171">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-171">Int64</span></span>|  
|<span data-ttu-id="9d8fc-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="9d8fc-173">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-173">String</span></span>|  
|<span data-ttu-id="9d8fc-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="9d8fc-175">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-175">String</span></span>|  
|<span data-ttu-id="9d8fc-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="9d8fc-177">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-177">String</span></span>|  
|<span data-ttu-id="9d8fc-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="9d8fc-179">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-179">String</span></span>|  
|<span data-ttu-id="9d8fc-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="9d8fc-181">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-181">String</span></span>|  
|<span data-ttu-id="9d8fc-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-182">COLLATION_NAME</span></span>|<span data-ttu-id="9d8fc-183">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-183">String</span></span>|  
|<span data-ttu-id="9d8fc-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="9d8fc-185">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-185">String</span></span>|  
|<span data-ttu-id="9d8fc-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="9d8fc-187">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-187">String</span></span>|  
|<span data-ttu-id="9d8fc-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-188">DOMAIN_NAME</span></span>|<span data-ttu-id="9d8fc-189">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-189">String</span></span>|  
|<span data-ttu-id="9d8fc-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-190">DESCRIPTION</span></span>|<span data-ttu-id="9d8fc-191">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-191">String</span></span>|  
|<span data-ttu-id="9d8fc-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-192">COLUMN_LCID</span></span>|<span data-ttu-id="9d8fc-193">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-193">Int32</span></span>|  
|<span data-ttu-id="9d8fc-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="9d8fc-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="9d8fc-195">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-195">Int32</span></span>|  
|<span data-ttu-id="9d8fc-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-196">COLUMN_SORTID</span></span>|<span data-ttu-id="9d8fc-197">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-197">Int32</span></span>|  
|<span data-ttu-id="9d8fc-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="9d8fc-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="9d8fc-199">Byte[]</span></span>|  
|<span data-ttu-id="9d8fc-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="9d8fc-200">IS_COMPUTED</span></span>|<span data-ttu-id="9d8fc-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="9d8fc-202">Procedure</span><span class="sxs-lookup"><span data-stu-id="9d8fc-202">Procedures</span></span>  
  
|<span data-ttu-id="9d8fc-203">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d8fc-203">ColumnName</span></span>|<span data-ttu-id="9d8fc-204">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d8fc-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d8fc-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9d8fc-206">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-206">String</span></span>|  
|<span data-ttu-id="9d8fc-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9d8fc-208">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-208">String</span></span>|  
|<span data-ttu-id="9d8fc-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="9d8fc-210">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-210">String</span></span>|  
|<span data-ttu-id="9d8fc-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9d8fc-212">Int16</span><span class="sxs-lookup"><span data-stu-id="9d8fc-212">Int16</span></span>|  
|<span data-ttu-id="9d8fc-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="9d8fc-214">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-214">String</span></span>|  
|<span data-ttu-id="9d8fc-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-215">DESCRIPTION</span></span>|<span data-ttu-id="9d8fc-216">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-216">String</span></span>|  
|<span data-ttu-id="9d8fc-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9d8fc-217">DATE_CREATED</span></span>|<span data-ttu-id="9d8fc-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d8fc-218">DateTime</span></span>|  
|<span data-ttu-id="9d8fc-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9d8fc-219">DATE_MODIFIED</span></span>|<span data-ttu-id="9d8fc-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d8fc-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="9d8fc-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9d8fc-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="9d8fc-222">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d8fc-222">ColumnName</span></span>|<span data-ttu-id="9d8fc-223">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d8fc-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d8fc-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9d8fc-225">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-225">String</span></span>|  
|<span data-ttu-id="9d8fc-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9d8fc-227">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-227">String</span></span>|  
|<span data-ttu-id="9d8fc-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="9d8fc-229">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-229">String</span></span>|  
|<span data-ttu-id="9d8fc-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-230">PARAMETER_NAME</span></span>|<span data-ttu-id="9d8fc-231">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-231">String</span></span>|  
|<span data-ttu-id="9d8fc-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d8fc-233">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-233">Int32</span></span>|  
|<span data-ttu-id="9d8fc-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="9d8fc-235">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-235">Int32</span></span>|  
|<span data-ttu-id="9d8fc-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="9d8fc-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="9d8fc-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-237">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="9d8fc-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="9d8fc-239">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-239">String</span></span>|  
|<span data-ttu-id="9d8fc-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-240">IS_NULLABLE</span></span>|<span data-ttu-id="9d8fc-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-241">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-242">DATA_TYPE</span></span>|<span data-ttu-id="9d8fc-243">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-243">Int32</span></span>|  
|<span data-ttu-id="9d8fc-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d8fc-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9d8fc-245">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-245">Int64</span></span>|  
|<span data-ttu-id="9d8fc-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d8fc-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9d8fc-247">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-247">Int64</span></span>|  
|<span data-ttu-id="9d8fc-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9d8fc-249">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-249">Int32</span></span>|  
|<span data-ttu-id="9d8fc-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="9d8fc-251">Int16</span><span class="sxs-lookup"><span data-stu-id="9d8fc-251">Int16</span></span>|  
|<span data-ttu-id="9d8fc-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-252">DESCRIPTION</span></span>|<span data-ttu-id="9d8fc-253">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-253">String</span></span>|  
|<span data-ttu-id="9d8fc-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-254">TYPE_NAME</span></span>|<span data-ttu-id="9d8fc-255">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-255">String</span></span>|  
|<span data-ttu-id="9d8fc-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="9d8fc-257">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="9d8fc-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="9d8fc-258">Catalog</span></span>  
  
|<span data-ttu-id="9d8fc-259">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d8fc-259">ColumnName</span></span>|<span data-ttu-id="9d8fc-260">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d8fc-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d8fc-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-261">CATALOG_NAME</span></span>|<span data-ttu-id="9d8fc-262">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-262">String</span></span>|  
|<span data-ttu-id="9d8fc-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-263">DESCRIPTION</span></span>|<span data-ttu-id="9d8fc-264">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="9d8fc-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="9d8fc-265">Indexes</span></span>  
  
|<span data-ttu-id="9d8fc-266">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d8fc-266">ColumnName</span></span>|<span data-ttu-id="9d8fc-267">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d8fc-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d8fc-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-268">TABLE_CATALOG</span></span>|<span data-ttu-id="9d8fc-269">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-269">String</span></span>|  
|<span data-ttu-id="9d8fc-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="9d8fc-271">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-271">String</span></span>|  
|<span data-ttu-id="9d8fc-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-272">TABLE_NAME</span></span>|<span data-ttu-id="9d8fc-273">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-273">String</span></span>|  
|<span data-ttu-id="9d8fc-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-274">INDEX_CATALOG</span></span>|<span data-ttu-id="9d8fc-275">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-275">String</span></span>|  
|<span data-ttu-id="9d8fc-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="9d8fc-277">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-277">String</span></span>|  
|<span data-ttu-id="9d8fc-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-278">INDEX_NAME</span></span>|<span data-ttu-id="9d8fc-279">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-279">String</span></span>|  
|<span data-ttu-id="9d8fc-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="9d8fc-280">PRIMARY_KEY</span></span>|<span data-ttu-id="9d8fc-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-281">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-282">UNIQUE</span></span>|<span data-ttu-id="9d8fc-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-283">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="9d8fc-284">CLUSTERED</span></span>|<span data-ttu-id="9d8fc-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-285">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-286">TYPE</span></span>|<span data-ttu-id="9d8fc-287">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-287">Int32</span></span>|  
|<span data-ttu-id="9d8fc-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="9d8fc-288">FILL_FACTOR</span></span>|<span data-ttu-id="9d8fc-289">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-289">Int32</span></span>|  
|<span data-ttu-id="9d8fc-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-290">INITIAL_SIZE</span></span>|<span data-ttu-id="9d8fc-291">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-291">Int32</span></span>|  
|<span data-ttu-id="9d8fc-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="9d8fc-292">NULLS</span></span>|<span data-ttu-id="9d8fc-293">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-293">Int32</span></span>|  
|<span data-ttu-id="9d8fc-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="9d8fc-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="9d8fc-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-295">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-296">AUTO_UPDATE</span></span>|<span data-ttu-id="9d8fc-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-297">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-298">NULL_COLLATION</span></span>|<span data-ttu-id="9d8fc-299">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-299">Int32</span></span>|  
|<span data-ttu-id="9d8fc-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d8fc-301">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-301">Int64</span></span>|  
|<span data-ttu-id="9d8fc-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-302">COLUMN_NAME</span></span>|<span data-ttu-id="9d8fc-303">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-303">String</span></span>|  
|<span data-ttu-id="9d8fc-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-304">COLUMN_GUID</span></span>|<span data-ttu-id="9d8fc-305">Guid</span><span class="sxs-lookup"><span data-stu-id="9d8fc-305">Guid</span></span>|  
|<span data-ttu-id="9d8fc-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-306">COLUMN_PROPID</span></span>|<span data-ttu-id="9d8fc-307">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-307">Int64</span></span>|  
|<span data-ttu-id="9d8fc-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-308">COLLATION</span></span>|<span data-ttu-id="9d8fc-309">Int16</span><span class="sxs-lookup"><span data-stu-id="9d8fc-309">Int16</span></span>|  
|<span data-ttu-id="9d8fc-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="9d8fc-310">CARDINALITY</span></span>|<span data-ttu-id="9d8fc-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="9d8fc-311">Decimal</span></span>|  
|<span data-ttu-id="9d8fc-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="9d8fc-312">PAGES</span></span>|<span data-ttu-id="9d8fc-313">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-313">Int32</span></span>|  
|<span data-ttu-id="9d8fc-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-314">FILTER_CONDITION</span></span>|<span data-ttu-id="9d8fc-315">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-315">String</span></span>|  
|<span data-ttu-id="9d8fc-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="9d8fc-316">INTEGRATED</span></span>|<span data-ttu-id="9d8fc-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="9d8fc-318">Provider OLE DB per Microsoft Oracle</span><span class="sxs-lookup"><span data-stu-id="9d8fc-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="9d8fc-319">Oltre alle raccolte di schemi comuni, il driver OLE DB per Microsoft Oracle supporta le seguenti raccolte di schemi specifici:</span><span class="sxs-lookup"><span data-stu-id="9d8fc-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="9d8fc-320">Tabelle</span><span class="sxs-lookup"><span data-stu-id="9d8fc-320">Tables</span></span>  
  
-   <span data-ttu-id="9d8fc-321">Colonne</span><span class="sxs-lookup"><span data-stu-id="9d8fc-321">Columns</span></span>  
  
-   <span data-ttu-id="9d8fc-322">Procedure</span><span class="sxs-lookup"><span data-stu-id="9d8fc-322">Procedures</span></span>  
  
-   <span data-ttu-id="9d8fc-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9d8fc-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="9d8fc-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9d8fc-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="9d8fc-325">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="9d8fc-325">Views</span></span>  
  
-   <span data-ttu-id="9d8fc-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="9d8fc-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="9d8fc-327">Tabelle</span><span class="sxs-lookup"><span data-stu-id="9d8fc-327">Tables</span></span>  
  
|<span data-ttu-id="9d8fc-328">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d8fc-328">ColumnName</span></span>|<span data-ttu-id="9d8fc-329">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d8fc-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d8fc-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-330">TABLE_CATALOG</span></span>|<span data-ttu-id="9d8fc-331">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-331">String</span></span>|  
|<span data-ttu-id="9d8fc-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="9d8fc-333">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-333">String</span></span>|  
|<span data-ttu-id="9d8fc-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-334">TABLE_NAME</span></span>|<span data-ttu-id="9d8fc-335">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-335">String</span></span>|  
|<span data-ttu-id="9d8fc-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-336">TABLE_TYPE</span></span>|<span data-ttu-id="9d8fc-337">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-337">String</span></span>|  
|<span data-ttu-id="9d8fc-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-338">TABLE_GUID</span></span>|<span data-ttu-id="9d8fc-339">Guid</span><span class="sxs-lookup"><span data-stu-id="9d8fc-339">Guid</span></span>|  
|<span data-ttu-id="9d8fc-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-340">DESCRIPTION</span></span>|<span data-ttu-id="9d8fc-341">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-341">String</span></span>|  
|<span data-ttu-id="9d8fc-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-342">TABLE_PROPID</span></span>|<span data-ttu-id="9d8fc-343">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-343">Int64</span></span>|  
|<span data-ttu-id="9d8fc-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9d8fc-344">DATE_CREATED</span></span>|<span data-ttu-id="9d8fc-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d8fc-345">DateTime</span></span>|  
|<span data-ttu-id="9d8fc-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9d8fc-346">DATE_MODIFIED</span></span>|<span data-ttu-id="9d8fc-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d8fc-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="9d8fc-348">Colonne</span><span class="sxs-lookup"><span data-stu-id="9d8fc-348">Columns</span></span>  
  
|<span data-ttu-id="9d8fc-349">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d8fc-349">ColumnName</span></span>|<span data-ttu-id="9d8fc-350">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d8fc-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d8fc-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-351">TABLE_CATALOG</span></span>|<span data-ttu-id="9d8fc-352">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-352">String</span></span>|  
|<span data-ttu-id="9d8fc-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="9d8fc-354">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-354">String</span></span>|  
|<span data-ttu-id="9d8fc-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-355">TABLE_NAME</span></span>|<span data-ttu-id="9d8fc-356">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-356">String</span></span>|  
|<span data-ttu-id="9d8fc-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-357">COLUMN_NAME</span></span>|<span data-ttu-id="9d8fc-358">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-358">String</span></span>|  
|<span data-ttu-id="9d8fc-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-359">COLUMN_GUID</span></span>|<span data-ttu-id="9d8fc-360">Guid</span><span class="sxs-lookup"><span data-stu-id="9d8fc-360">Guid</span></span>|  
|<span data-ttu-id="9d8fc-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-361">COLUMN_PROPID</span></span>|<span data-ttu-id="9d8fc-362">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-362">Int64</span></span>|  
|<span data-ttu-id="9d8fc-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d8fc-364">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-364">Int64</span></span>|  
|<span data-ttu-id="9d8fc-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="9d8fc-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="9d8fc-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-366">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="9d8fc-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="9d8fc-368">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-368">String</span></span>|  
|<span data-ttu-id="9d8fc-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="9d8fc-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="9d8fc-370">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-370">Int64</span></span>|  
|<span data-ttu-id="9d8fc-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-371">IS_NULLABLE</span></span>|<span data-ttu-id="9d8fc-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-372">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-373">DATA_TYPE</span></span>|<span data-ttu-id="9d8fc-374">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-374">Int32</span></span>|  
|<span data-ttu-id="9d8fc-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-375">TYPE_GUID</span></span>|<span data-ttu-id="9d8fc-376">Guid</span><span class="sxs-lookup"><span data-stu-id="9d8fc-376">Guid</span></span>|  
|<span data-ttu-id="9d8fc-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d8fc-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9d8fc-378">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-378">Int64</span></span>|  
|<span data-ttu-id="9d8fc-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d8fc-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9d8fc-380">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-380">Int64</span></span>|  
|<span data-ttu-id="9d8fc-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9d8fc-382">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-382">Int32</span></span>|  
|<span data-ttu-id="9d8fc-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="9d8fc-384">Int16</span><span class="sxs-lookup"><span data-stu-id="9d8fc-384">Int16</span></span>|  
|<span data-ttu-id="9d8fc-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="9d8fc-386">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-386">Int64</span></span>|  
|<span data-ttu-id="9d8fc-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="9d8fc-388">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-388">String</span></span>|  
|<span data-ttu-id="9d8fc-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="9d8fc-390">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-390">String</span></span>|  
|<span data-ttu-id="9d8fc-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="9d8fc-392">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-392">String</span></span>|  
|<span data-ttu-id="9d8fc-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="9d8fc-394">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-394">String</span></span>|  
|<span data-ttu-id="9d8fc-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="9d8fc-396">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-396">String</span></span>|  
|<span data-ttu-id="9d8fc-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-397">COLLATION_NAME</span></span>|<span data-ttu-id="9d8fc-398">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-398">String</span></span>|  
|<span data-ttu-id="9d8fc-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="9d8fc-400">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-400">String</span></span>|  
|<span data-ttu-id="9d8fc-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="9d8fc-402">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-402">String</span></span>|  
|<span data-ttu-id="9d8fc-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-403">DOMAIN_NAME</span></span>|<span data-ttu-id="9d8fc-404">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-404">String</span></span>|  
|<span data-ttu-id="9d8fc-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-405">DESCRIPTION</span></span>|<span data-ttu-id="9d8fc-406">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="9d8fc-407">Procedure</span><span class="sxs-lookup"><span data-stu-id="9d8fc-407">Procedures</span></span>  
  
|<span data-ttu-id="9d8fc-408">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d8fc-408">ColumnName</span></span>|<span data-ttu-id="9d8fc-409">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d8fc-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d8fc-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9d8fc-411">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-411">String</span></span>|  
|<span data-ttu-id="9d8fc-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9d8fc-413">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-413">String</span></span>|  
|<span data-ttu-id="9d8fc-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="9d8fc-415">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-415">String</span></span>|  
|<span data-ttu-id="9d8fc-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9d8fc-417">Int16</span><span class="sxs-lookup"><span data-stu-id="9d8fc-417">Int16</span></span>|  
|<span data-ttu-id="9d8fc-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="9d8fc-419">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-419">String</span></span>|  
|<span data-ttu-id="9d8fc-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-420">DESCRIPTION</span></span>|<span data-ttu-id="9d8fc-421">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-421">String</span></span>|  
|<span data-ttu-id="9d8fc-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9d8fc-422">DATE_CREATED</span></span>|<span data-ttu-id="9d8fc-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d8fc-423">DateTime</span></span>|  
|<span data-ttu-id="9d8fc-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9d8fc-424">DATE_MODIFIED</span></span>|<span data-ttu-id="9d8fc-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d8fc-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="9d8fc-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="9d8fc-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="9d8fc-427">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d8fc-427">ColumnName</span></span>|<span data-ttu-id="9d8fc-428">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d8fc-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d8fc-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9d8fc-430">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-430">String</span></span>|  
|<span data-ttu-id="9d8fc-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9d8fc-432">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-432">String</span></span>|  
|<span data-ttu-id="9d8fc-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="9d8fc-434">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-434">String</span></span>|  
|<span data-ttu-id="9d8fc-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-435">COLUMN_NAME</span></span>|<span data-ttu-id="9d8fc-436">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-436">String</span></span>|  
|<span data-ttu-id="9d8fc-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-437">COLUMN_GUID</span></span>|<span data-ttu-id="9d8fc-438">Guid</span><span class="sxs-lookup"><span data-stu-id="9d8fc-438">Guid</span></span>|  
|<span data-ttu-id="9d8fc-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-439">COLUMN_PROPID</span></span>|<span data-ttu-id="9d8fc-440">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-440">Int64</span></span>|  
|<span data-ttu-id="9d8fc-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="9d8fc-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="9d8fc-442">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-442">Int64</span></span>|  
|<span data-ttu-id="9d8fc-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d8fc-444">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-444">Int64</span></span>|  
|<span data-ttu-id="9d8fc-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-445">IS_NULLABLE</span></span>|<span data-ttu-id="9d8fc-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-446">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-447">DATA_TYPE</span></span>|<span data-ttu-id="9d8fc-448">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-448">Int32</span></span>|  
|<span data-ttu-id="9d8fc-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-449">TYPE_GUID</span></span>|<span data-ttu-id="9d8fc-450">Guid</span><span class="sxs-lookup"><span data-stu-id="9d8fc-450">Guid</span></span>|  
|<span data-ttu-id="9d8fc-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d8fc-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9d8fc-452">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-452">Int64</span></span>|  
|<span data-ttu-id="9d8fc-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d8fc-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9d8fc-454">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-454">Int64</span></span>|  
|<span data-ttu-id="9d8fc-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9d8fc-456">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-456">Int32</span></span>|  
|<span data-ttu-id="9d8fc-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="9d8fc-458">Int16</span><span class="sxs-lookup"><span data-stu-id="9d8fc-458">Int16</span></span>|  
|<span data-ttu-id="9d8fc-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-459">DESCRIPTION</span></span>|<span data-ttu-id="9d8fc-460">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-460">String</span></span>|  
|<span data-ttu-id="9d8fc-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="9d8fc-461">OVERLOAD</span></span>|<span data-ttu-id="9d8fc-462">Int16</span><span class="sxs-lookup"><span data-stu-id="9d8fc-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="9d8fc-463">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="9d8fc-463">Views</span></span>  
  
|<span data-ttu-id="9d8fc-464">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d8fc-464">ColumnName</span></span>|<span data-ttu-id="9d8fc-465">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d8fc-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d8fc-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-466">TABLE_CATALOG</span></span>|<span data-ttu-id="9d8fc-467">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-467">String</span></span>|  
|<span data-ttu-id="9d8fc-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="9d8fc-469">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-469">String</span></span>|  
|<span data-ttu-id="9d8fc-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-470">TABLE_NAME</span></span>|<span data-ttu-id="9d8fc-471">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-471">String</span></span>|  
|<span data-ttu-id="9d8fc-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="9d8fc-473">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-473">String</span></span>|  
|<span data-ttu-id="9d8fc-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-474">CHECK_OPTION</span></span>|<span data-ttu-id="9d8fc-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-475">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-476">IS_UPDATABLE</span></span>|<span data-ttu-id="9d8fc-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-477">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-478">DESCRIPTION</span></span>|<span data-ttu-id="9d8fc-479">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-479">String</span></span>|  
|<span data-ttu-id="9d8fc-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9d8fc-480">DATE_CREATED</span></span>|<span data-ttu-id="9d8fc-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d8fc-481">DateTime</span></span>|  
|<span data-ttu-id="9d8fc-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9d8fc-482">DATE_MODIFIED</span></span>|<span data-ttu-id="9d8fc-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d8fc-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="9d8fc-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="9d8fc-484">Indexes</span></span>  
  
|<span data-ttu-id="9d8fc-485">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d8fc-485">ColumnName</span></span>|<span data-ttu-id="9d8fc-486">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d8fc-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d8fc-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-487">TABLE_CATALOG</span></span>|<span data-ttu-id="9d8fc-488">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-488">String</span></span>|  
|<span data-ttu-id="9d8fc-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="9d8fc-490">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-490">String</span></span>|  
|<span data-ttu-id="9d8fc-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-491">TABLE_NAME</span></span>|<span data-ttu-id="9d8fc-492">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-492">String</span></span>|  
|<span data-ttu-id="9d8fc-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-493">INDEX_CATALOG</span></span>|<span data-ttu-id="9d8fc-494">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-494">String</span></span>|  
|<span data-ttu-id="9d8fc-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="9d8fc-496">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-496">String</span></span>|  
|<span data-ttu-id="9d8fc-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-497">INDEX_NAME</span></span>|<span data-ttu-id="9d8fc-498">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-498">String</span></span>|  
|<span data-ttu-id="9d8fc-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="9d8fc-499">PRIMARY_KEY</span></span>|<span data-ttu-id="9d8fc-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-500">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-501">UNIQUE</span></span>|<span data-ttu-id="9d8fc-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-502">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="9d8fc-503">CLUSTERED</span></span>|<span data-ttu-id="9d8fc-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-504">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-505">TYPE</span></span>|<span data-ttu-id="9d8fc-506">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-506">Int32</span></span>|  
|<span data-ttu-id="9d8fc-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="9d8fc-507">FILL_FACTOR</span></span>|<span data-ttu-id="9d8fc-508">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-508">Int32</span></span>|  
|<span data-ttu-id="9d8fc-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-509">INITIAL_SIZE</span></span>|<span data-ttu-id="9d8fc-510">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-510">Int32</span></span>|  
|<span data-ttu-id="9d8fc-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="9d8fc-511">NULLS</span></span>|<span data-ttu-id="9d8fc-512">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-512">Int32</span></span>|  
|<span data-ttu-id="9d8fc-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="9d8fc-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="9d8fc-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-514">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-515">AUTO_UPDATE</span></span>|<span data-ttu-id="9d8fc-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-516">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-517">NULL_COLLATION</span></span>|<span data-ttu-id="9d8fc-518">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-518">Int32</span></span>|  
|<span data-ttu-id="9d8fc-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d8fc-520">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-520">Int64</span></span>|  
|<span data-ttu-id="9d8fc-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-521">COLUMN_NAME</span></span>|<span data-ttu-id="9d8fc-522">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-522">String</span></span>|  
|<span data-ttu-id="9d8fc-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-523">COLUMN_GUID</span></span>|<span data-ttu-id="9d8fc-524">Guid</span><span class="sxs-lookup"><span data-stu-id="9d8fc-524">Guid</span></span>|  
|<span data-ttu-id="9d8fc-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-525">COLUMN_PROPID</span></span>|<span data-ttu-id="9d8fc-526">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-526">Int64</span></span>|  
|<span data-ttu-id="9d8fc-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-527">COLLATION</span></span>|<span data-ttu-id="9d8fc-528">Int16</span><span class="sxs-lookup"><span data-stu-id="9d8fc-528">Int16</span></span>|  
|<span data-ttu-id="9d8fc-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="9d8fc-529">CARDINALITY</span></span>|<span data-ttu-id="9d8fc-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="9d8fc-530">Decimal</span></span>|  
|<span data-ttu-id="9d8fc-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="9d8fc-531">PAGES</span></span>|<span data-ttu-id="9d8fc-532">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-532">Int32</span></span>|  
|<span data-ttu-id="9d8fc-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-533">FILTER_CONDITION</span></span>|<span data-ttu-id="9d8fc-534">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-534">String</span></span>|  
|<span data-ttu-id="9d8fc-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="9d8fc-535">INTEGRATED</span></span>|<span data-ttu-id="9d8fc-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="9d8fc-537">Provider OLE DB per Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="9d8fc-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="9d8fc-538">Oltre alle raccolte di schemi comuni, il driver OLE DB di Microsoft Jet supporta le raccolte di schemi specifici seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d8fc-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="9d8fc-539">Tabelle</span><span class="sxs-lookup"><span data-stu-id="9d8fc-539">Tables</span></span>  
  
-   <span data-ttu-id="9d8fc-540">Colonne</span><span class="sxs-lookup"><span data-stu-id="9d8fc-540">Columns</span></span>  
  
-   <span data-ttu-id="9d8fc-541">Procedure</span><span class="sxs-lookup"><span data-stu-id="9d8fc-541">Procedures</span></span>  
  
-   <span data-ttu-id="9d8fc-542">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="9d8fc-542">Views</span></span>  
  
-   <span data-ttu-id="9d8fc-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="9d8fc-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="9d8fc-544">Tabelle</span><span class="sxs-lookup"><span data-stu-id="9d8fc-544">Tables</span></span>  
  
|<span data-ttu-id="9d8fc-545">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d8fc-545">ColumnName</span></span>|<span data-ttu-id="9d8fc-546">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d8fc-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d8fc-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-547">TABLE_CATALOG</span></span>|<span data-ttu-id="9d8fc-548">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-548">String</span></span>|  
|<span data-ttu-id="9d8fc-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="9d8fc-550">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-550">String</span></span>|  
|<span data-ttu-id="9d8fc-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-551">TABLE_NAME</span></span>|<span data-ttu-id="9d8fc-552">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-552">String</span></span>|  
|<span data-ttu-id="9d8fc-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-553">TABLE_TYPE</span></span>|<span data-ttu-id="9d8fc-554">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-554">String</span></span>|  
|<span data-ttu-id="9d8fc-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-555">TABLE_GUID</span></span>|<span data-ttu-id="9d8fc-556">Guid</span><span class="sxs-lookup"><span data-stu-id="9d8fc-556">Guid</span></span>|  
|<span data-ttu-id="9d8fc-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-557">DESCRIPTION</span></span>|<span data-ttu-id="9d8fc-558">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-558">String</span></span>|  
|<span data-ttu-id="9d8fc-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-559">TABLE_PROPID</span></span>|<span data-ttu-id="9d8fc-560">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-560">Int64</span></span>|  
|<span data-ttu-id="9d8fc-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9d8fc-561">DATE_CREATED</span></span>|<span data-ttu-id="9d8fc-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d8fc-562">DateTime</span></span>|  
|<span data-ttu-id="9d8fc-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9d8fc-563">DATE_MODIFIED</span></span>|<span data-ttu-id="9d8fc-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d8fc-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="9d8fc-565">Colonne</span><span class="sxs-lookup"><span data-stu-id="9d8fc-565">Columns</span></span>  
  
|<span data-ttu-id="9d8fc-566">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d8fc-566">ColumnName</span></span>|<span data-ttu-id="9d8fc-567">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d8fc-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d8fc-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-568">TABLE_CATALOG</span></span>|<span data-ttu-id="9d8fc-569">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-569">String</span></span>|  
|<span data-ttu-id="9d8fc-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="9d8fc-571">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-571">String</span></span>|  
|<span data-ttu-id="9d8fc-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-572">TABLE_NAME</span></span>|<span data-ttu-id="9d8fc-573">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-573">String</span></span>|  
|<span data-ttu-id="9d8fc-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-574">COLUMN_NAME</span></span>|<span data-ttu-id="9d8fc-575">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-575">String</span></span>|  
|<span data-ttu-id="9d8fc-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-576">COLUMN_GUID</span></span>|<span data-ttu-id="9d8fc-577">Guid</span><span class="sxs-lookup"><span data-stu-id="9d8fc-577">Guid</span></span>|  
|<span data-ttu-id="9d8fc-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-578">COLUMN_PROPID</span></span>|<span data-ttu-id="9d8fc-579">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-579">Int64</span></span>|  
|<span data-ttu-id="9d8fc-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d8fc-581">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-581">Int64</span></span>|  
|<span data-ttu-id="9d8fc-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="9d8fc-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="9d8fc-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-583">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="9d8fc-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="9d8fc-585">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-585">String</span></span>|  
|<span data-ttu-id="9d8fc-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="9d8fc-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="9d8fc-587">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-587">Int64</span></span>|  
|<span data-ttu-id="9d8fc-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-588">IS_NULLABLE</span></span>|<span data-ttu-id="9d8fc-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-589">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-590">DATA_TYPE</span></span>|<span data-ttu-id="9d8fc-591">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-591">Int32</span></span>|  
|<span data-ttu-id="9d8fc-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-592">TYPE_GUID</span></span>|<span data-ttu-id="9d8fc-593">Guid</span><span class="sxs-lookup"><span data-stu-id="9d8fc-593">Guid</span></span>|  
|<span data-ttu-id="9d8fc-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d8fc-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="9d8fc-595">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-595">Int64</span></span>|  
|<span data-ttu-id="9d8fc-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="9d8fc-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="9d8fc-597">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-597">Int64</span></span>|  
|<span data-ttu-id="9d8fc-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="9d8fc-599">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-599">Int32</span></span>|  
|<span data-ttu-id="9d8fc-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="9d8fc-601">Int16</span><span class="sxs-lookup"><span data-stu-id="9d8fc-601">Int16</span></span>|  
|<span data-ttu-id="9d8fc-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="9d8fc-603">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-603">Int64</span></span>|  
|<span data-ttu-id="9d8fc-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="9d8fc-605">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-605">String</span></span>|  
|<span data-ttu-id="9d8fc-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="9d8fc-607">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-607">String</span></span>|  
|<span data-ttu-id="9d8fc-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="9d8fc-609">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-609">String</span></span>|  
|<span data-ttu-id="9d8fc-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="9d8fc-611">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-611">String</span></span>|  
|<span data-ttu-id="9d8fc-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="9d8fc-613">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-613">String</span></span>|  
|<span data-ttu-id="9d8fc-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-614">COLLATION_NAME</span></span>|<span data-ttu-id="9d8fc-615">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-615">String</span></span>|  
|<span data-ttu-id="9d8fc-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="9d8fc-617">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-617">String</span></span>|  
|<span data-ttu-id="9d8fc-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="9d8fc-619">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-619">String</span></span>|  
|<span data-ttu-id="9d8fc-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-620">DOMAIN_NAME</span></span>|<span data-ttu-id="9d8fc-621">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-621">String</span></span>|  
|<span data-ttu-id="9d8fc-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-622">DESCRIPTION</span></span>|<span data-ttu-id="9d8fc-623">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="9d8fc-624">Procedure</span><span class="sxs-lookup"><span data-stu-id="9d8fc-624">Procedures</span></span>  
  
|<span data-ttu-id="9d8fc-625">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d8fc-625">ColumnName</span></span>|<span data-ttu-id="9d8fc-626">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d8fc-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d8fc-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="9d8fc-628">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-628">String</span></span>|  
|<span data-ttu-id="9d8fc-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="9d8fc-630">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-630">String</span></span>|  
|<span data-ttu-id="9d8fc-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="9d8fc-632">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-632">String</span></span>|  
|<span data-ttu-id="9d8fc-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="9d8fc-634">Int16</span><span class="sxs-lookup"><span data-stu-id="9d8fc-634">Int16</span></span>|  
|<span data-ttu-id="9d8fc-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="9d8fc-636">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-636">String</span></span>|  
|<span data-ttu-id="9d8fc-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-637">DESCRIPTION</span></span>|<span data-ttu-id="9d8fc-638">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-638">String</span></span>|  
|<span data-ttu-id="9d8fc-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9d8fc-639">DATE_CREATED</span></span>|<span data-ttu-id="9d8fc-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d8fc-640">DateTime</span></span>|  
|<span data-ttu-id="9d8fc-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9d8fc-641">DATE_MODIFIED</span></span>|<span data-ttu-id="9d8fc-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d8fc-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="9d8fc-643">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="9d8fc-643">Views</span></span>  
  
|<span data-ttu-id="9d8fc-644">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d8fc-644">ColumnName</span></span>|<span data-ttu-id="9d8fc-645">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d8fc-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d8fc-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-646">TABLE_CATALOG</span></span>|<span data-ttu-id="9d8fc-647">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-647">String</span></span>|  
|<span data-ttu-id="9d8fc-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="9d8fc-649">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-649">String</span></span>|  
|<span data-ttu-id="9d8fc-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-650">TABLE_NAME</span></span>|<span data-ttu-id="9d8fc-651">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-651">String</span></span>|  
|<span data-ttu-id="9d8fc-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="9d8fc-653">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-653">String</span></span>|  
|<span data-ttu-id="9d8fc-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-654">CHECK_OPTION</span></span>|<span data-ttu-id="9d8fc-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-655">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-656">IS_UPDATABLE</span></span>|<span data-ttu-id="9d8fc-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-657">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-658">DESCRIPTION</span></span>|<span data-ttu-id="9d8fc-659">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-659">String</span></span>|  
|<span data-ttu-id="9d8fc-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="9d8fc-660">DATE_CREATED</span></span>|<span data-ttu-id="9d8fc-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d8fc-661">DateTime</span></span>|  
|<span data-ttu-id="9d8fc-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="9d8fc-662">DATE_MODIFIED</span></span>|<span data-ttu-id="9d8fc-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="9d8fc-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="9d8fc-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="9d8fc-664">Indexes</span></span>  
  
|<span data-ttu-id="9d8fc-665">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="9d8fc-665">ColumnName</span></span>|<span data-ttu-id="9d8fc-666">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d8fc-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="9d8fc-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-667">TABLE_CATALOG</span></span>|<span data-ttu-id="9d8fc-668">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-668">String</span></span>|  
|<span data-ttu-id="9d8fc-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="9d8fc-670">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-670">String</span></span>|  
|<span data-ttu-id="9d8fc-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-671">TABLE_NAME</span></span>|<span data-ttu-id="9d8fc-672">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-672">String</span></span>|  
|<span data-ttu-id="9d8fc-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9d8fc-673">INDEX_CATALOG</span></span>|<span data-ttu-id="9d8fc-674">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-674">String</span></span>|  
|<span data-ttu-id="9d8fc-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9d8fc-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="9d8fc-676">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-676">String</span></span>|  
|<span data-ttu-id="9d8fc-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-677">INDEX_NAME</span></span>|<span data-ttu-id="9d8fc-678">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-678">String</span></span>|  
|<span data-ttu-id="9d8fc-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="9d8fc-679">PRIMARY_KEY</span></span>|<span data-ttu-id="9d8fc-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-680">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-681">UNIQUE</span></span>|<span data-ttu-id="9d8fc-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-682">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="9d8fc-683">CLUSTERED</span></span>|<span data-ttu-id="9d8fc-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-684">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-685">TYPE</span></span>|<span data-ttu-id="9d8fc-686">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-686">Int32</span></span>|  
|<span data-ttu-id="9d8fc-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="9d8fc-687">FILL_FACTOR</span></span>|<span data-ttu-id="9d8fc-688">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-688">Int32</span></span>|  
|<span data-ttu-id="9d8fc-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-689">INITIAL_SIZE</span></span>|<span data-ttu-id="9d8fc-690">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-690">Int32</span></span>|  
|<span data-ttu-id="9d8fc-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="9d8fc-691">NULLS</span></span>|<span data-ttu-id="9d8fc-692">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-692">Int32</span></span>|  
|<span data-ttu-id="9d8fc-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="9d8fc-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="9d8fc-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-694">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="9d8fc-695">AUTO_UPDATE</span></span>|<span data-ttu-id="9d8fc-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="9d8fc-696">Boolean</span></span>|  
|<span data-ttu-id="9d8fc-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-697">NULL_COLLATION</span></span>|<span data-ttu-id="9d8fc-698">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-698">Int32</span></span>|  
|<span data-ttu-id="9d8fc-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="9d8fc-700">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-700">Int64</span></span>|  
|<span data-ttu-id="9d8fc-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9d8fc-701">COLUMN_NAME</span></span>|<span data-ttu-id="9d8fc-702">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-702">String</span></span>|  
|<span data-ttu-id="9d8fc-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-703">COLUMN_GUID</span></span>|<span data-ttu-id="9d8fc-704">Guid</span><span class="sxs-lookup"><span data-stu-id="9d8fc-704">Guid</span></span>|  
|<span data-ttu-id="9d8fc-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="9d8fc-705">COLUMN_PROPID</span></span>|<span data-ttu-id="9d8fc-706">Int64</span><span class="sxs-lookup"><span data-stu-id="9d8fc-706">Int64</span></span>|  
|<span data-ttu-id="9d8fc-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-707">COLLATION</span></span>|<span data-ttu-id="9d8fc-708">Int16</span><span class="sxs-lookup"><span data-stu-id="9d8fc-708">Int16</span></span>|  
|<span data-ttu-id="9d8fc-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="9d8fc-709">CARDINALITY</span></span>|<span data-ttu-id="9d8fc-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="9d8fc-710">Decimal</span></span>|  
|<span data-ttu-id="9d8fc-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="9d8fc-711">PAGES</span></span>|<span data-ttu-id="9d8fc-712">Int32</span><span class="sxs-lookup"><span data-stu-id="9d8fc-712">Int32</span></span>|  
|<span data-ttu-id="9d8fc-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="9d8fc-713">FILTER_CONDITION</span></span>|<span data-ttu-id="9d8fc-714">String</span><span class="sxs-lookup"><span data-stu-id="9d8fc-714">String</span></span>|  
|<span data-ttu-id="9d8fc-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="9d8fc-715">INTEGRATED</span></span>|<span data-ttu-id="9d8fc-716">Booleano</span><span class="sxs-lookup"><span data-stu-id="9d8fc-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d8fc-717">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d8fc-717">See also</span></span>
- [<span data-ttu-id="9d8fc-718">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="9d8fc-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
