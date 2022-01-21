# total belanjaan tokped

langkah pertama buka 
`https://www.tokopedia.com/order-list`

kedua buat var total =0
`total_all=0;`

total per page dengan query selector
`totalperpage=[...document.querySelectorAll(".sum-price>div>p:nth-child(2)")].map(e=> parseInt(e.innerText.replace("Rp","").replace(".","").replace(".","").replace(".","").trim())).reduce((a,b)=>a=a+b,0);`

jumlahkan total_all dari total per page
`total_all=total_all+totalperpage; `

selector next halaman
`document.querySelector("button[aria-label='Halaman berikutnya']").click();`

urutan pengerjaan
> bikin total all=0
> loop :
> total perpage
> add total per page to total all
> next page
> loop until you finish

full script
`totalperpage=[...document.querySelectorAll(".sum-price>div>p:nth-child(2)")].map(e=> parseInt(e.innerText.replace("Rp","").replace(".","").replace(".","").replace(".","").trim())).reduce((a,b)=>a=a+b,0); total_all=total_all+totalperpage; document.querySelector("button[aria-label='Halaman berikutnya']").click();total_all;`
