## Laravel Auth Multi Guard Level And IsActive
Clone Project :
1. https://github.com/azmrfii/Laravel_Auth_Multi_Guard_Level_IsActive.git
2. composer install
3. cp .env.example .env
4. Sesuaikan database di file .env
5. php artisan config:cache
6. php artisan key:generate
7. php artisan migrate

Middleware Check Level
if ($request->user()->level == 'admin')
{
    return $next($request);
}
if ($request->user()->level == 'petugas')
{
    return $next($request);
}
    return redirect()->route('login');
    
Middleware IsActive
if(Auth::user()->status == 1) {
    return $next($request);
}
    return redirect()->route('login');
