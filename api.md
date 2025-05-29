Route::get('/', function () {
    return view('welcome');
})->name('home');

/* Login y registro */
Route::post('/api/register', [RegisterController::class, 'register']);
Route::post('/api/login', [LoginController::class, 'login']);

Route::middleware([JwtMiddleware::class])->group(function () {

    /* Mostrar usuarios */
    Route::get('/api/users', [IndexUserController::class, '__invoke']);
    Route::get('/api/users/{id}', [ShowUserController::class, '__invoke']);

    /* Crear usuario */
    Route::post('/api/users/createUser', [StoreUserController::class, '__invoke']);

    /* Editar Usuario*/
    Route::put('/api/users/updateUser/{id}', [UpdateUserController::class, '__invoke']);

    /*Borrar Usuario*/
    Route::delete('/api/auth/users/{id}', [DeleteUserController::class, '__invoke']);


    /* Mostrar clientes */
    Route::get('/api/customers', [IndexCustomerController::class, '__invoke']);
    Route::get('/api/customers/{id}', [ShowCustomerController::class, '__invoke']);

    /* Crear cliente */
    Route::post('/api/customers/createCustomer', [StoreCustomerController::class, '__invoke']);

    /* Editar cliente */
    Route::put('/api/customers/updateCustomer/{id}', [UpdateCustomerController::class, '__invoke']);

    /* Borrar cliente */
    Route::delete('/api/auth/customers/{id}', [DeleteCustomerController::class, '__invoke']);


    /* Mostrar proyectos */
    Route::get('/api/projects', [IndexProjectController::class, '__invoke']);
    Route::get('/api/projects/{id}', [ShowProjectController::class, '__invoke']);

    /* Crear proyecto */
    Route::post('/api/projects/createProject', [StoreProjectController::class, '__invoke']);

    /* Editar proyecto */
    Route::put('/api/projects/updateProject/{id}', [UpdateProjectController::class, '__invoke']);

    /* Borrar proyecto */
    Route::delete('/api/auth/projects/{id}', [DeleteProjectController::class, '__invoke']);

    /* Mostrar tareas */
    Route::get('/api/tasks', [IndexTaskController::class, '__invoke']);
    Route::get('/api/tasks/{id}', [ShowTaskController::class, '__invoke']);

    /* Crear tarea */
    Route::post('/api/tasks/createTask', [StoreTaskController::class, '__invoke']);

    /* Editar tarea */
    Route::put('/api/tasks/updateTask/{id}', [UpdateTaskController::class, '__invoke']);

    /* Borrar tarea */
    Route::delete('/api/auth/tasks/{id}', [DeleteTaskController::class, '__invoke']);

    /*Mostrar time entries*/
    Route::get('/api/tasks/{id}/time-entries', [IndexTimeEntryController::class, '__invoke']);
    Route::get('/api/auth/time-entries/{id}', [ShowTimeEntryController::class, '__invoke']);

    /*Crear time entries*/
    Route::post('/api/time-entries/createTimeEntry', [StoreTimeEntryController::class, '__invoke']);

    /*Editar time entries*/
    Route::put('/api/time-entries/{id}/updateTimeEntry', [UpdateTimeEntryController::class, '__invoke']);

    /*Borrar time entries*/
    Route::delete('/api/auth/time-entries/{id}', [DeleteTimeEntryController::class, '__invoke']);

    /*Mostrar comentarios*/
    Route::get('/api/tasks/{id}/comments', [IndexCommentController::class, '__invoke']);
    Route::get('/api/auth/comments/{id}', [ShowCommentController::class, '__invoke']);

    /*Crear comentarios*/
    Route::post('/api/comments/createComment', [StoreCommentController::class, '__invoke']);

    /*Editar comentarios*/
    Route::put('/api/comments/{id}/updateComment', [UpdateCommentController::class, '__invoke']);

    /*Borrar comentarios*/
    Route::delete('/api/auth/comments/{id}', [DeleteCommentController::class, '__invoke']);

    /*Mostrar archivos*/
    Route::get('/api/tasks/{id}/attachments', [IndexAttachmentController::class, '__invoke']);

    /*Subir archivos*/
    Route::post('/api/attachments/{id}/createAttachment', [StoreAttachmentController::class, '__invoke']);

    /*Descargar archivos*/
    Route::get('/api/attachments/{id}/downloadAttachment', [DownloadAttachmentController::class, '__invoke']);

    /*Borrar archivo*/
    Route::delete('/api/auth/attachments/{id}', [DeleteAttachmentController::class, '__invoke']);

    /*Mostrar tareas en dashboard*/
    Route::get('/api/dashboard/tasks', [UserPendingTasksController::class, '__invoke']);

    /*Proyectos activos*/
    Route::get('/api/dashboard/projects', [UserActiveProjectsController::class, '__invoke']);

    /*Actividades recientes*/
    Route::get('/api/dashboard/comments', [RecentActivitiesController::class, '__invoke']);

    /*Listar notificaciones*/
    Route::get('/api/auth/notifications/count-unread', [CountUnreadNotificationsController::class, '__invoke']);

    Route::get('/api/auth/notifications/{id}', [IndexUserNotificationController::class, '__invoke']);

    Route::put('/api/auth/notifications/{notificationId}/mark-as-readed', [MarkNotificationAsReadController::class, '__invoke']);

    Route::put('/api/auth/notifications/{id}/mark-all-readed', [MarkAllNotificationsAsReadController::class, '__invoke']);

    Route::view('dashboard', 'dashboard')
        ->middleware(['auth', 'verified'])
        ->name('dashboard');
});

Route::middleware(['auth'])->group(function () {
    Route::redirect('settings', 'settings/profile');

    /*Route::get('settings/profile', Profile::class)->name('settings.profile');
    Route::get('settings/password', Password::class)->name('settings.password');
    Route::get('settings/appearance', Appearance::class)->name('settings.appearance');
*/});
