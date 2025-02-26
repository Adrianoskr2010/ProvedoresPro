# ProvedoresProimport React from 'react';
import { Card, CardContent } from '@/components/ui/card';
import { Button } from '@/components/ui/button';

const products = [
  { name: 'Pro 2', originalPrice: 10, discountPrice: 5, image: '/images/pro2_img.png' },
  { name: 'Camiseta de Fútbol', originalPrice: 10, discountPrice: 5, image: '/images/camiseta_img.png' }
];

const HomePage = () => {
  return (
    <div className='bg-black text-white min-h-screen'>
      <header className='text-center p-4 bg-black'>
        <img src='/images/saturno.png' alt='Saturno' className='mx-auto w-48 h-48 object-cover'/>
        <h1 className='text-3xl font-bold text-yellow-500'>ProvedoresPro</h1>
        <p>¡ACEPTAMOS PAGOS CONTRAREEMBOLSO!</p>
      </header>
      <section className='grid grid-cols-1 md:grid-cols-2 gap-4 p-4'>
        {products.map((product) => (
          <Card key={product.name} className='bg-gray-800 text-white'>
            <img src={product.image} alt={product.name} className='w-full h-48 object-cover'/>
            <CardContent>
              <h2 className='text-xl font-bold'>{product.name}</h2>
              <p className='line-through text-gray-500'>€{product.originalPrice}</p>
              <p className='text-yellow-500'>€{product.discountPrice}</p>
              <Button className='mt-2 bg-yellow-500 hover:bg-yellow-600 text-black'>Comprar</Button>
            </CardContent>
          </Card>
        ))}
      </section>
    </div>
  );
};

export default HomePage;
