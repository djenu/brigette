const product[
{
id:1,
name:"pagne wax Africain",
descriction:"pagne traditionnel Africain",
price: 17000 fcfa,
image:"pagne1.jpg"
},
id:2,
name:"pagne kente",
description:"pagne traditionnel ghana",
price: 24000 fcfa,
image:"pagne2.jpg"
},
{
id:3,
name:"pagne bazin riche",
description:"pagne traditionnel senegalais en coton",
price: 21000 fcfa,
image:"pagne3.jpg"
function displayproducts(){
const productgrid=document.queryselector("product-grid");
productproducts.forEach(product=>{
const productElement=document.createElement("div"); 
productElement.classList.add("product");

conct imageElement= document.createElement("img");
Element src=product.image;
imageElement.alt= product.name;

const nameElement=document.createElement("h3")
nameElement.textcontent= 'prix:(product.price)fcfa';
const addToCartButton=document.createElement("p");
addToCartButton.textcontent="ajouter au panier";
addToCartButton.addEventListener("click",():=>addToCart(product));

productElement appendChild(imageElement);
productElement appendChild(nameElement);
productElement appendChild(descriptionElement);
productElement appendChild(priceElement);
productElement appendChild(addToCartButton);

productElement appendChild(productElement);
});
}

function addToCart(product){
let cart=JSON.parse(LocalStorage.getItem("cart")) || [];
const existingProduct=cart.find(item => item.id === product.id);
if(existingProduct){
existingProduct.quantity++;
}
else{
cart.push({ ...product,quantity:1});
}
localStorage.setitem("cart",JSON.stringify(cart));
alert('fcfa{product.name} a été ajouté à votre panier.');
}


